In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named xfusioncorp.sh. While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 3 within the Stratos Datacenter.

Your task is to grant executable permissions to the /tmp/xfusioncorp.sh script on App Server 3. Additionally, ensure that all users have the capability to execute it.

```
chmod 755 /tmp/xfusioncorp.sh
sudo chmod 755 /tmp/xfusioncorp.sh
sh /tmp/xfusioncorp.sh
```
