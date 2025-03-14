This application operates on port 6200, and firewalld is active on the server. To meet operational needs, the following requirements have been identified:

Allow all incoming connections on port 6200/tcp. Ensure the zone is set to public.

```
sudo firewall-cmd --zone=public --add-port=6200/tcp --permanent
sudo firewall-cmd --reload
```
