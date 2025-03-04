After conducting a security audit within the Stratos DC, the Nautilus security team discovered misconfigured permissions on critical files. To address this, corrective actions are being taken by the production support team. Specifically, the file named /etc/hostname on Nautilus App 2 server requires adjustments to its Access Control Lists (ACLs) as follows:

1. The file's user owner and group owner should be set to root.

2. Others should possess read only permissions on the file.

3. User rose must not have any permissions on the file.

4. User garrett should be granted read only permission on the file.

```
sudo chown root:root /etc/hostname
sudo chmod 644 /etc/hostname   or sudo chmod o=r /etc/hostname
sudo setfacl -m u:rose:--- /etc/hostname
sudo setfacl -m u:garrett:r-- /etc/hostname
getfacl /etc/hostname
setfacl --help
history | cut -c 8-

```
