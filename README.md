# Zabbix-Traceroute

# Como Instalar

vim /etc/zabbix/zabbix_server.conf
Timeout = 30

apt install mtr-tiny

cd /usr/lib/zabbix/externalscripts

echo '#!/bin/bash' > zbx_mtr

echo 'IP=$1' >> zbx_mtr

echo 'mtr -r -c5 -w -b -p -j $IP | sed -e "s/???/* * */g"' >> zbx_mtr

chown zabbix. zbx_mtr  

chmod +x zbx_mtr
