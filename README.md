Close the file when you are finished editing. Make it executable with the following command:
```
chmod +x ssl_renew.sh
```
Next, open your root crontab file to run the renewal script at a specified interval:
```
sudo crontab -e 
```
At the very bottom of this file, add the following line:

```crontab
<!-- every 5 minutes for testing -->
*/5 * * * * /home/sammy/wordpress/ssl_renew.sh >> /var/log/cron.log 2>&1
<!-- every day-->
0 12 * * * /home/sammy/wordpress/ssl_renew.sh >> /var/log/cron.log 2>&1
```