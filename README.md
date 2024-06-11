# zabbix7

 Installation  steps
 ```
root@zabbix:/etc/zabbix# history
    1  clear
    2  cd /tmp/
    3  wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_7.0-1+ubuntu22.04_all.deb
    4  ls
    5  dpkg -i zabbix-release_7.0-1+ubuntu22.04_all.deb
    6  apt update
    7  apt install zabbix-server-mysql zabbix-frontend-php zabbix-nginx-conf zabbix-sql-scripts zabbix-agent
    8  apt install mysql-server
    9  mysql -uroot -p
   10  zcat /usr/share/zabbix-sql-scripts/mysql/server.sql.gz | mysql --default-character-set=utf8mb4 -uzabbix -p zabbix
   11  mysql -uroot -p
   12  vi /etc/zabbix/zabbix_server.conf
   13  vi ~/.vimrc
   14  vi /etc/zabbix/zabbix_server.conf
   15  cd /etc/zabbix
   16  openssl req -newkey rsa:4096 -x509 -sha256 -days 3650 -nodes -out 192.168.200.103.crt -keyout 192.168.200.103.key
   17  vi /etc/zabbix/nginx.conf
   18  nginx -t
   19  systemctl restart zabbix-server zabbix-agent nginx php8.1-fpm
   20  systemctl enable zabbix-server zabbix-agent nginx php8.1-fpm
   21  systemctl restart nginx
   22  clear
   23  cat /etc/lsb-release
   24  apt update && apt upgrade
   25  wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
   26  dpkg -i google-chrome-stable_current_amd64.deb
   27  sudo apt -f install
   28  dpkg -i google-chrome-stable_current_amd64.deb
   29  google-chrome --version
   30  pip3 install selenium
   31  apt install python3-pip
   32  pip3 install webdriver-manager
   33  vim test.py
   34  python3 test.py
   35  pip3 test.py
   36  ls
   37  python3 test.py
   38  vi test.py
   39  sudo pip3 install selenium
   40  python3 test.py
   41  vi zabbix_server.conf
   42  systemctl restart zabbix-server
   43  echo $JAVA_HOME
   44  which java
   45  update-alternatives --config java
   46  java --version
   47  apt install openjdk-18-jre-headless
   48  java --version
   49  update-alternatives --config java
   50  export JAVA_HOME=/usr/lib/jvm/java-18-openjdk-amd64/
   51  echo $JAVA_HOME
   52  systemctl restart zabbix-server
   53  webdriver-manager start
   54  node webdriver-manager start
   55  apt install nodejs
   56  node webdriver-manager start
   57  updatedb
   58  apt install plocate
   59  locate webdriver-manager
   60  node webdriver-manager start
   61  locate webdriver
   62  webdriver --start
   63  cd /usr/local/lib/python3.10/dist-packages/
   64  node webdriver-manager start
   65  webdriver-manager start
   66  locate node_modules
   67  cd ../../../../
   68  webdriver-manager updat
   69  pip3 webdriver-manager start
   70  pip3 webdriver-manager
   71  pip3 install webdriver-manager
   72  pip list
   73  webdriver-manager update --ignore_ssl --proxy
   74  apt install npm
   75  npm install webdriver-manager
   76  webdriver-manager start
   77  npm update
   78  npm audit
   79  vi  /root/.npm/_logs/2024-06-11T01_29_55_154Z-debug-0.log
   80  sudo npm install -g npm@7.7.0
   81  clear
   82  webdriver-manager start
   83  npm install -g webdriver-manager
   84  webdriver-manager update
   85  webdriver-manager start
   86  cd /etc/zabbix/
   87  vi zabbix_server.conf
   88  webdriver-manager start
```
