# Description
Check PgBouncer status and LLD pools.  
Check pools metrics. 
# Dependencies
psql, bash, zabbix-agent.

Installation
============
0. /etc/pgbouncer/userlist.txt  - add user and pass  "zabbix" "zabbix"
   /etc/pgbouncer/pgbouncer.ini - stats_users = zabbix
1. create directory and copy pgbouncer.sh to /var/lib/zabbix/
   change homedir for zabbix user usermod -d /var/lib/zabbix zabbix
2. copy zabbix_agentd.d/pgbouncer.conf to /etc/zabbix/zabbix_agentd.d/
3. chmod 755 /var/lib/zabbix/externalscripts/pgbouncer.sh and chown zabbix.zabbix /var/lib/zabbix/pgbouncer.sh
4. copy file .pgpass.j2 to /etc/zabbix/.pgpass and edit monitoring user and password, if needed, port too.
5. chmod 0600 /etc/zabbix/.pgpass and chown zabbix.zabbix ~zabbix/.pgpass
6. restart zabbix-agent daemon.
7. import "zbx_templates/Template App PgBouncer.xml" into your templates.
8. apply template "Template App PgBouncer" to pgbouncer node.





