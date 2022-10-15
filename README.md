# session-record


# steps 1

vim /etc/profile

##……………………………………………………##
if [ "x$SESSION_RECORD" = "x" ]
then
timestamp=$(date +%d-%m-%Y-%T)
session_log=/var/log/session/session.$USER.$$.$timestamp
SESSION_RECORD=started
export SESSION_RECORD
script -t -f -q 2>${session_log}.timing $session_log
exit
fi
##……………………………………………………##


save and exit


mkdir -p /var/log/session


chmod 777 /var/log/session



