# Hibernation
A few things I've discovered for hibernation, mainly in Ubuntu 20.04/10+(?). 

## Enable hibernation, swap to disk (not partition)

Here is what I did to make it work with Ubuntu 18.04.

-   Make your `/swapfile` have at least the size of your RAM

```
sudo swapoff /swapfile
sudo dd if=/dev/zero of=/swapfile bs=$(cat /proc/meminfo | awk '/MemTotal/ {print $2}') count=1024 conv=notrunc
sudo mkswap /swapfile
sudo swapon /swapfile
```

-   Note the UUID of the partition containing your `/swapfile`:

```
$ sudo findmnt -no UUID -T /swapfile
20562a02-cfa6-42e0-bb9f-5e936ea763d0
```

-   Reconfigure the package `uswsusp` in order to correctly use the swapfile:

```
sudo dpkg-reconfigure -pmedium uswsusp
# Answer "Yes" to continue without swap space
# Select "/dev/disk/by-uuid/20562a02-cfa6-42e0-bb9f-5e936ea763d0" replace the UUID with the result from the previous findmnt command
# Encrypt: "No"
```

-   Edit the SystemD hibernate service using `sudo systemctl edit systemd-hibernate.service` and fill it with the following content:

```
[Service]
ExecStart=
ExecStartPre=-/bin/run-parts -v -a pre /lib/systemd/system-sleep
ExecStart=/usr/sbin/s2disk
ExecStartPost=-/bin/run-parts -v --reverse -a post /lib/systemd/system-sleep
```

-   Note the resume offset of your `/swapfile`:

```
$ sudo swap-offset /swapfile
resume offset = 34818
```

-   Configure Grub to resume from the swapfile by editing `/etc/default/grub` and modify the following line:

```
GRUB_CMDLINE_LINUX_DEFAULT="resume=UUID=20562a02-cfa6-42e0-bb9f-5e936ea763d0 resume_offset=34818 quiet splash"
```

-   Update Grub:

```
sudo update-grub
```

-   Create the following `/etc/initramfs-tools/conf.d/resume`:

```
RESUME=UUID=20562a02-cfa6-42e0-bb9e-5e936ea763d0 resume_offset=34816
    # Resume from /swapfile

```

-   Update initramfs:

```
sudo update-initramfs -u -k all
```

Now you can hibernate with `sudo systemctl hibernate`.

One can also create those scripts:

```
sudo tee /usr/local/bin/gotosleep <<EOF
dbus-send --type=method_call --dest=org.gnome.ScreenSaver /org/gnome/ScreenSaver org.gnome.ScreenSaver.Lock
sleep 2
sudo /usr/sbin/s2both
EOF
sudo chmod +x /usr/local/bin/gotosleep
sudo tee /usr/local/bin/gotohibernation <<EOF
dbus-send --type=method_call --dest=org.gnome.ScreenSaver /org/gnome/ScreenSaver org.gnome.ScreenSaver.Lock
sleep 2
sudo systemctl hibernate
EOF
sudo chmod +x /usr/local/bin/gotohibernation
```

So you can sleep with `gotosleep` or hibernate with `gotohibernation`.

You must be able to execute `sudo s2both`, `sudo s2ram` and `sudo systemctl hibernate`without having to enter your password for the previous scripts to work.

You could do that for example by creating a `powerdev` group, add your current user to it, and configure the following sudoers config (edit it with `sudo visudo -f /etc/sudoers.d/powerdev`):

```
%powerdev ALL=NOPASSWD: /usr/sbin/s2both, /usr/sbin/s2ram, /bin/systemctl hibernate

```

Documentation used:

-   [Cas' answer](https://askubuntu.com/a/892410/29219)
-   [Debian "Hibernate without swap partition"](https://wiki.debian.org/Hibernation/Hibernate_Without_Swap_Partition)
-   [Configuring Lubuntu 18.04 to enable hibernation using a swap file](https://fitzcarraldoblog.wordpress.com/2018/07/14/configuring-lubuntu-18-04-to-enable-hibernation-using-a-swap-file/)
-   [So question "s2disk works, but hibernation from menu gets stuck afer login"](https://askubuntu.com/q/1035345/29219)

## Enable suspend then hibernate 
This enables ubuntu/linux to suspend then after a set amount of time hibernaate

To start using this function (suspend-then-hibernate) you need to create a file ```/etc/systemd/sleep.conf``` with the next content:

```
[Sleep]
HibernateDelaySec=3600
```
Then you can test it by command:

```sudo systemctl suspend-then-hibernate```

you can edit ```HibernateDelaySec``` to reduce delay to hibernate.

If all works fine you can change Lid Close Action, to do it you need to edit the file ```/etc/systemd/logind.conf```

You need to find option ```HandleLidSwitch=```, uncomment it and change to ```HandleLidSwitch=suspend-then-hibernate```. Then you need to restart systemd-logind service (warning! you user session will be restarted) by the next command:

```sudo systemctl restart systemd-logind.service```

That's all! Now you can use this nice function. (via [StackOverflow](https://askubuntu.com/questions/12383/how-to-go-automatically-from-suspend-into-hibernate))
