# zabbix-7.0

 Installation  steps

Download and unzip repo
```
wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-1+ubuntu22.04_all.deb
```
```
dpkg -i zabbix-release_7.0-1+ubuntu22.04_all.deb
```
Update repo
```
apt update
```
Install apackages

```
apt install zabbix-server-mysql zabbix-frontend-php zabbix-nginx-conf zabbix-sql-scripts zabbix-agent
```
Install Database, start and enable on boot.
```
apt install mysql-server
```
```
systemctl start mysql.service
```
```
systemctl enable mysql.service
```
Create zabbix database.

```
mysql -uroot -p
```
Install  database config.
```
zcat /usr/share/zabbix-sql-scripts/mysql/server.sql.gz | mysql --default-character-set=utf8mb4 -uzabbix -p zabbix
```
Adjust  Zabbix configuration file.
```
vi /etc/zabbix/zabbix_server.conf
```
Remove  colored text in files.
```
vi ~/.vimrc
```
Add to file and save/exit
```
syntax off
```
Change directory

```
cd /etc/zabbix
```

Create certificates.
```
openssl req -newkey rsa:4096 -x509 -sha256 -days 3650 -nodes -out 192.168.200.103.crt -keyout 192.168.1.112.key
```
Nginx configration.
```
vi /etc/zabbix/nginx.conf
```
test config.
```
nginx -t
```
Start zabbix services.
```
systemctl restart zabbix-server zabbix-agent nginx php8.1-fpm
```
Enable service on boot
```
systemctl enable zabbix-server zabbix-agent nginx php8.1-fpm
```

Installation for  Website by Browser

NOTE: 

https://www.initmax.com/wiki/installation-and-basic-usage-of-browser-item/

http://archive.ubuntu.com/ubuntu/pool/universe/g/golang-github-containernetworking-plugins/

Install Podman
```
apt install podman
```
Install Podman-compose.

```
pip3 install podman-compose
```
Install pip

```
apt install python3-pip
```
Get docker compose file.
```
wget https://raw.githubusercontent.com/SeleniumHQ/docker-selenium/trunk/docker-compose-v3-full-grid.yml -O docker-compose.yml
```
```
# To execute this docker compose yml file use `docker compose -f docker-compose-v3-full-grid.yml up`
# Add the `-d` flag at the end for detached execution
# To stop the execution, hit Ctrl+C, and then `docker compose -f docker-compose-v3-full-grid.yml down`
version: "3"
services:
  selenium-event-bus:
    image: selenium/event-bus:4.28.1-20250202
    container_name: selenium-event-bus
    ports:
      - "4442:4442"
      - "4443:4443"
      - "5557:5557"

  selenium-sessions:
    image: selenium/sessions:4.28.1-20250202
    container_name: selenium-sessions
    ports:
      - "5556:5556"
    depends_on:
      - selenium-event-bus
    environment:
      - SE_EVENT_BUS_HOST=selenium-event-bus
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443

  selenium-session-queue:
    image: selenium/session-queue:4.28.1-20250202
    container_name: selenium-session-queue
    ports:
      - "5559:5559"

  selenium-distributor:
    image: selenium/distributor:4.28.1-20250202
    container_name: selenium-distributor
    ports:
      - "5553:5553"
    depends_on:
      - selenium-event-bus
      - selenium-sessions
      - selenium-session-queue
    environment:
      - SE_EVENT_BUS_HOST=selenium-event-bus
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443
      - SE_SESSIONS_MAP_HOST=selenium-sessions
      - SE_SESSIONS_MAP_PORT=5556
      - SE_SESSION_QUEUE_HOST=selenium-session-queue
      - SE_SESSION_QUEUE_PORT=5559

  selenium-router:
    image: selenium/router:4.28.1-20250202
    container_name: selenium-router
    ports:
      - "4444:4444"
    depends_on:
      - selenium-distributor
      - selenium-sessions
      - selenium-session-queue
    environment:
      - SE_DISTRIBUTOR_HOST=selenium-distributor
      - SE_DISTRIBUTOR_PORT=5553
      - SE_SESSIONS_MAP_HOST=selenium-sessions
      - SE_SESSIONS_MAP_PORT=5556
      - SE_SESSION_QUEUE_HOST=selenium-session-queue
      - SE_SESSION_QUEUE_PORT=5559

  chrome:
    image: selenium/node-chrome:4.28.1-20250202
    shm_size: 2gb
    depends_on:
      - selenium-event-bus
    environment:
      - SE_EVENT_BUS_HOST=selenium-event-bus
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443

  edge:
    image: selenium/node-edge:4.28.1-20250202
    shm_size: 2gb
    depends_on:
      - selenium-event-bus
    environment:
      - SE_EVENT_BUS_HOST=selenium-event-bus
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443

  firefox:
    image: selenium/node-firefox:4.28.1-20250202
    shm_size: 2gb
    depends_on:
      - selenium-event-bus
    environment:
      - SE_EVENT_BUS_HOST=selenium-event-bus
      - SE_EVENT_BUS_PUBLISH_PORT=4442
      - SE_EVENT_BUS_SUBSCRIBE_PORT=4443
```
Get Plugin
```
wget http://archive.ubuntu.com/ubuntu/pool/universe/g/golang-github-containernetworking-plugins/containernetworking-plugins_1.1.1+ds1-3_amd64.deb
```
Install package
```
dpkg -i containernetworking-plugins_1.1.1+ds1-3_amd64.deb
```
Install Docker Compose
```
apt install docker-compose
```
Start Docker container.

```
docker-compose  -f docker-compose.yml up -d
```
```
docker-compose up -d
```
```
dpcker-compose ps  
```
Adjust Zabbix configuration file
```
vi zabbix_server.conf
```
Start and enable services.
```
systemctl restart zabbix-server
```
```
systemctl enable zabbix-server
```

