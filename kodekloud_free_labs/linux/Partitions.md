list no of disks

list space on particular disk

how to crreat gpt partition of 500 MB

```
lsblk
fdisk -l
gdisk /dev/vdb
n
default
500+
Choose a partition type (e.g., 8300 for Linux).
w

```
