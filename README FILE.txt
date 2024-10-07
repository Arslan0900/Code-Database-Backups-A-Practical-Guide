critical info like password store into this file  ~/.my.cnf
open this file with this command nano ~/.my.cnf
store the info init like 
"[client] 
 user=ac_user 
 password=123 "
secure the file "chmod 600 ~/.my.cnf"

now for scheduling these files use 
crontab -e
and add these line to run these files daily 
0 0 * * * /opt/ac-code-backup.sh >> /var/log/ac-code-backup.log 2>&1
0 0 * * * /opt/ac-db-backup.sh >> /var/log/ac-db-backup.log 2>&1
