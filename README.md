# zabbix-hpacucli
Monitoring HP Smart Array Controller in Zabbix
Its a simple script to monitor controller and disk with hpacucli.
In HP Gen9 you have to use hpssacli instead of hpacucli 

#Installation 
1) Install hpacucli

2) Add Zabbix in Sudoers list :
```bash
## Allow zabbix some limited usage of the hpacucli tool
zabbix ALL=NOPASSWD:/usr/sbin/hpacucli ctrl all show status
zabbix ALL=NOPASSWD:/usr/sbin/hpacucli ctrl slot=0 pd all show
```
3) Add check_hpacucli in /usr/local/bin , note that if you change script path edit userparameter file.

4) copy userparameter_hpacucli.conf in your zabbix agent config directory (for me : /etc/zabbix/zabbix_agentd.d)

5) Restart Agent. 

keys are : 
hpacucli_ctrlstat
hpacucli_diskstat

Thanks to sven : http://sven.stormbind.net/misc/tnotes/zabbixhpacucli.html

Feel free to make this little script work better .




