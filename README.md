# zabbix-7.0

 Installation  steps
 
 ```
root@zabbix:/etc/zabbix# history
wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-1+ubuntu22.04_all.deb
dpkg -i zabbix-release_7.0-1+ubuntu22.04_all.deb
apt update
apt install zabbix-server-mysql zabbix-frontend-php zabbix-nginx-conf zabbix-sql-scripts zabbix-agent
apt install mysql-server
systemctl start mysql.service
mysql -uroot -p
zcat /usr/share/zabbix-sql-scripts/mysql/server.sql.gz | mysql --default-character-set=utf8mb4 -uzabbix -p zabbix
mysql -uroot -p
vi /etc/zabbix/zabbix_server.conf
vi ~/.vimrc
vi /etc/zabbix/zabbix_server.conf
cd /etc/zabbix
openssl req -newkey rsa:4096 -x509 -sha256 -days 3650 -nodes -out 192.168.200.103.crt -keyout 192.168.200.103.key
vi /etc/zabbix/nginx.conf
nginx -t
systemctl restart zabbix-server zabbix-agent nginx php8.1-fpm
systemctl enable zabbix-server zabbix-agent nginx php8.1-fpm
```

Installation for  Website by Browser

NOTE: 

https://www.initmax.com/wiki/installation-and-basic-usage-of-browser-item/
http://archive.ubuntu.com/ubuntu/pool/universe/g/golang-github-containernetworking-plugins/

```
apt install podman 
pip3 install podman-compose
apt install python3-pip
wget https://raw.githubusercontent.com/SeleniumHQ/docker-selenium/trunk/docker-compose-v3-full-grid.yml -O docker-compose.yml
wget http://archive.ubuntu.com/ubuntu/pool/universe/g/golang-github-containernetworking-plugins/containernetworking-plugins_1.1.1+ds1-3_amd64.deb
dpkg -i containernetworking-plugins_1.1.1+ds1-3_amd64.deb
apt install docker-compose
docker-compose  -f docker-compose.yml up -d
# docker-compose up -d
dpcker-compose ps  
vi zabbix_server.conf
systemctl restart zabbix-server
```
