### Database

#### instalasi

```
Pacman -S mariadb
```
```
sudo systemctl start mariadb
```
```
sudo systemctl enable mariadb
```

#### prepare database

```
sudo mysql_secure_installation
```
```
mysql -u root
```
```
create database slimsdb;
```
```
create user slims_user;
```
```
grant all privileges on slimsdb.* to 'slims_user'@'localhost' identified by '1810';
```
```
flush privileges;
```
```
exit
```


### Apache 
install apache terlebih dahulu

```
pacman -S apache
```

lalu seetelah install cofig di apache
```
vim /etc/h
```
```
vim /etc/httpd/conf/httpd.conf
```
comennting :
```
#LoadModule mpm_event_module modules/mod_mpm_event.so
```
uncommenting:
```
LoadModule mpm_prefork_module modules/mod_mpm_prefork.so
```
```
vim /etc/httpd/conf/httpd.conf
```
tambahakan di paling bawah daftar LoadModule 

```
LoadModule php_module modules/libphp.so
```
```
AddHandler php-script .php
```

tambahkan di paling bawah daftar include

```
Include conf/extra/php_module.conf
```
```
cat etc/fstab
```

#### restart httpd
```
vim /etc/fstab
```
```
cd /srv/http
```
```
ls
```
```
cd .
```
```
cd ..
```
```
rm -fr http/*
```
```
systemctl restart httpd
```
```
cd http/
```
```
ls
```

### install wget slims

```
wget http://github.com//slims/slims9_bulian/releases/download/v9.6.0/slims9_bulian-9.6.0.tar.gz
```



