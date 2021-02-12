## Shell Tools, explained

### Kill JBoss (for example) process dynamically

`kill -9 ``ps -ef |grep jboss|grep -v grep |cut -c7-15|sed 's/ //g'`` `

`sed 's/ //g'`: trims the whitespace

`cut -c7-15`: extracts content from 7th to 15th character. This is username specific (has 6 characters in the example)

`grep -v grep`: excludes lines containing grep, with purpose to not list this comand itself

`grep jboss`: all the processes having jboss in their description

`ps -ef`: list all processes

` `` `: outputs result of this command as a string

`kill -9`: kills the process

### Recursive Grep

`grep -r --include "*.txt" texthere .`

### Grep for multiple patterns

This will grep text.log for one of 3 patterns: "Request", "Response" or "soap:Envelope"

`grep -E -- 'Request|Response|<soap:Envelope' text.log`

### Restart Cinammon without closing windows

cinammon --replace

### Restart VBox copy-paste 

`sudo killall VBoxClient`

`sudo VBoxClient-All`

### cron - edit, reload, check logs

Define cron tasks:

` crontab -e`
or
`sudo crontab -e`

Reload cron configuration:

`sudo service cron reload`

Verify that cron logging is enabled:
`vi /etc/rsyslog.conf`
Restart rsyslog to take new config into account:
`sudo service rsyslog restart`

Check cron log (file defined in rsyslog.conf)
`vi /var/log/cron.log`

Replace `cron` with `anacron` that will catch up with jobs that didn't execute due to computer being turned off:

`sudo apt-get update && sudo apt-get install anacron`

### Filesystem reserved space
`tune2fs -l /dev/disk |grep Reserved` ( this will tell you the current reserved blocks) 

`tune2fs -m 1 /dev/disk` ( sets reserved space to 1% in /dev/disk; replace /dev/disk with partition that is full) 

`tune2fs -m 5 /dev/disk` ( return reserved block count to 5%)

### Rotate logs manually

`sudo logrotate -d /etc/logrotate.conf`

