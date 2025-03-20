Install SElinux on rhel. Disable it and it should remain disabled after reboot.

```
sudo yum install policycoreutils selinux-policy libselinux
vi /etc/selinux/config
```

change SELINUX=disabled
