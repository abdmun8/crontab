# crontab
## Backup mysql database and add to gz file

<pre>
mysqldump -h DB_HOST -u proj_akm -pDB_PASS --databases DB_NAME | sed -e 's/DEFINER[ ]*=[ ]*[^*]**/*/' > /root/backup_db/DB_NAME-`date +\%Y\%m\%d`.sql && gzip -c /root/backup_db/DB_NAME-`date +\%Y\%m\%d`.sql > DB_NAME-`date +\%Y\%m\%d`.gz && rm /root/backup_db/DB_NAME-`date +\%Y\%m\%d`.sql
</pre>
