To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. Here's your task:

Create a user named javed with a non-interactive shell on App Server 1.

#### Solution
```
adduser --help | grep shell
adduser javed -s /sbin/nologin
id javed
cat /etc/passwd | grep -i javed
```
