# Ubuntu

## Batch import all missing GPG keys

Solves issues with GPG keys on major OS updates by grabbing and replacing **all** missing creds from the keyserver.

There's no need to change any part of the command, just run it as is. 

The command runs `sudo apt update` to update your software sources and detect missing GPG keys, then imports each missing key using [hkp://pool.sks-keyservers.net:80](https://sks-keyservers.net/) as its server, you could change this to any keyserver you feel most comfortable with ([http://keyserver.ubuntu.com](keyserver.ubuntu.com) is a possibility, but I've always had issues with it). 

The command also uses an array to store missing GPG keys for which we've already imported the key. Without that, the key import command would run twice for each missing key.

```bash
sudo apt update 2>&1 1>/dev/null | sed -ne 's/.*NO_PUBKEY //p' | while read key; do if ! [[ ${keys[*]} =~ "$key" ]]; then sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net:80 --recv-keys "$key"; keys+=("$key"); fi; done
```
