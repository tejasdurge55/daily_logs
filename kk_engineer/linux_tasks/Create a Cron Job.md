install cronie , start crond.service and create cronjob for root user `*/5 * * * * echo hello > /tmp/cron_text`

```
sudo su
yum install cronie -y
systemctl start crond
crontab -e
crontab -l

```
