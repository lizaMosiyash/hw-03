# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Солдатенкова Елизавета`


### Задание 1

![Скриншот админки](https://github.com/lizaMosiyash/screenshots/blob/main/login_zabbix.PNG)

* sudo wget https://repo.zabbix.com/zabbix/6.4/debian/pool/main/z/zabbix-release/zabbix-release_6.4-1+debian11_all.deb
* sudo dpkg -i zabbix-release_6.4-1+debian11_all.deb
* sudo apt update
* sudo apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
* sudo -u postgres createuser --pwprompt zabbix
* sudo -u postgres createdb -O zabbix zabbix
* sudo zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
* sudo nano /etc/zabbix/zabbix_server.conf 
* sudo systemctl restart zabbix-server zabbix-agent apache2
* sudo systemctl enable zabbix-server zabbix-agent apache2

---

### Задание 2

![Список хостов](https://github.com/lizaMosiyash/screenshots/blob/main/hosts.PNG)
![Лог](https://github.com/lizaMosiyash/screenshots/blob/main/log_zabbix_agent.PNG)
![Latest data](https://github.com/lizaMosiyash/screenshots/blob/main/latest_data.PNG)

*На втором хосте*
* sudo wget https://repo.zabbix.com/zabbix/6.4/debian/pool/main/z/zabbix-release/zabbix-release_6.4-1+debian11_all.deb
* sudo dpkg -i zabbix-release_6.4-1+debian11_all.deb
* sudo apt update
* sudo apt install zabbix-agent
* sudo systemctl restart zabbix-agent
* sudo systemctl enable zabbix-agent