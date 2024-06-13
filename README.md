# zabbix7

 Installation  steps
 ```
root@zabbix:/etc/zabbix# history
    1  clear
    2  wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-1+ubuntu22.04_all.deb
    3  dpkg -i zabbix-release_7.0-1+ubuntu22.04_all.deb
    4  apt update
    5  apt install zabbix-server-mysql zabbix-frontend-php zabbix-nginx-conf zabbix-sql-scripts zabbix-agent
    6  apt install mysql-server
    7  systemctl start mysql.service
    8  mysql -uroot -p
    9  zcat /usr/share/zabbix-sql-scripts/mysql/server.sql.gz | mysql --default-character-set=utf8mb4 -uzabbix -p zabbix
   10  mysql -uroot -p
   11  vi /etc/zabbix/zabbix_server.conf
   12  vi ~/.vimrc
   13  vi /etc/zabbix/zabbix_server.conf
   14  cd /etc/zabbix
   15  openssl req -newkey rsa:4096 -x509 -sha256 -days 3650 -nodes -out 192.168.200.103.crt -keyout 192.168.200.103.key
   16  vi /etc/zabbix/nginx.conf
   17  nginx -t
   18  systemctl restart zabbix-server zabbix-agent nginx php8.1-fpm
   19  systemctl enable zabbix-server zabbix-agent nginx php8.1-fpm
   20  clear
   21  dnf -y update
   22  apt install dnf
   23  dnf -y install podman podman-compose
   24  apt update
   25  apt install podman podman-compose
   26  sudo apt install -y podman
   27  pip3 install podman-compose
   28  apt install python3-pip
   29  pip3 install podman-compose
   30  wget https://raw.githubusercontent.com/SeleniumHQ/docker-selenium/trunk/docker-compose-v3-full-grid.yml -O docker-compose.yml
   31  ls
   32  podman-compose up -d
   33  podman ps
   34  podman network create -d bridge test-net
   35  podman network ls
   36  podman-compose up -d
   37  ls /etc/cni/net.d/test-net.conflist
   38  wget http://archive.ubuntu.com/ubuntu/pool/universe/g/golang-github-containernetworking-plugins/containernetworking-plugins_1.1.1+ds1-3_amd64.deb
   39  ls
   40  history
   41  ls
   42  dpkg -i containernetworking-plugins_1.1.1+ds1-3_amd64.deb
   43  podman-compose up -d
   44  podman ps
   45  ls
   46  wget https://raw.githubusercontent.com/SeleniumHQ/docker-selenium/trunk/docker-compose-v3-full-grid.yml -O docker-compose.yml
   47  ls
   48  vi docker-compose.yml
   49  podman-compose up -d
   50  podman compose --file compose.yaml up --detach
   51  ls
   52  podman compose --file docker-compose.yml up --detach
   53  podman compose -f docker-compose.yml up --detach
   54  docker-compose  -f docker-compose.yml up --detach
   55  apt  install docker-compose
   56  docker-compose  -f docker-compose.yml up
   57  docker-compose up -d
   58  podman ps
   59  dpcker-compose ps
   60  docker-compose ps
   61  vi zabbix_server.conf
   62  systemctl restart zabbix-server
   63  history


```
