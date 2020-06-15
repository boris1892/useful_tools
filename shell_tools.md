## Shell Tools, explained

`kill -9 ``ps -ef |grep jboss|grep -v grep |cut -c7-15|sed 's/ //g'`` `

`sed 's/ //g'`: trims the whitespace

`cut -c7-15`: extracts content from 7th to 15th character. This is username specific (has 6 characters in the example)

`grep -v grep`: excludes lines containing grep, with purpose to not list this comand itself

`grep jboss`: all the processes having jboss in their description

`ps -ef`: list all processes

` ``  `` `: outputs result of this command as a string

`kill -9`: kills the process
