# OneDrive

Rclone for virtual file system storage (cloud storage shouldn't download until you want them, in most cases). This is a startup script to unmount fuser on login (in case it didn't unmount properly on logout, shudown, or unexpected power loss) and then it instantiates the mount protocol for the virtual file system (vfs) with proper cacheing via Rclone.

This solves the issue of "transport endpoint is not connected" as well due to the unmounting call. 

```sh -c "fusermount -uz ~/OneDrive; rclone --vfs-cache-mode writes mount OneDrive: ~/OneDrive"```'
