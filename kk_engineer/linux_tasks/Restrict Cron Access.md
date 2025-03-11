 Allow crontab access to rose user while denying access to the garrett user.

```
echo "rose" | sudo tee -a /etc/cron.allow
echo "garrett" | sudo tee -a /etc/cron.deny
```
