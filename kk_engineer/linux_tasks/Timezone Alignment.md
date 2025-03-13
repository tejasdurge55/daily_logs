In the daily standup, it was noted that the timezone settings across the Nautilus Application Servers in the Stratos Datacenter are inconsistent with the local datacenter's timezone, currently set to Europe/Athens.



Synchronize the timezone settings to match the local datacenter's timezone (Europe/Athens).

```
sudo timedatectl set-timezone Europe/Athens
```
