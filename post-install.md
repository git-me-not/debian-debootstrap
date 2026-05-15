# using tmpfs for /tmp (RAM-based, so the content will be erased after reboot)

1. add this entries to /etc/fstab
```tmpfs /tmp tmpfs rw,nosuid,nodev,mode=1777,size=2G 0 0``` 
