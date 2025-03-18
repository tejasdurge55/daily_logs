Please set the maximum process limits as specified below:

for user: nfsuser 

a. Set the soft limit to 1024

b. Set the hard limit to 2025

```
sudo nano /etc/security/limits.conf

Add the following lines at the end of the file:
nfsuser soft nproc 1024
nfsuser hard nproc 2025
```
