The system admin team at xFusionCorp Industries has streamlined access management by implementing group-based access control. Here's what you need to do:

a. Create a group named nautilus_admin_users across all App servers within the Stratos Datacenter.

b. Add the user kano into the nautilus_admin_users group on all App servers. If the user doesn't exist, create it as well.

```
sudo su
sudo groupadd nautilus_admin_users
sudo adduser kano -g nautilus_admin_users
```
