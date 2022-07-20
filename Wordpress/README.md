
## Wordpress Installation

### Prerequisites:
 
 - A sudo user account (root privileges)
 -  LAMP stack
 
#### Required Versions of LAMP stack:

|LAMP|VERSIONS|
|---|---|
|Linux| Centos-7|
|Apache|--|
|Mariadb|10.5 or greater|
|PHP|7.4 or greater|

A LAMP stack is a collection of open-source software bundled and installed to enable a server to provide web resources.  Consinsting of Linux, Apache,MySQL, and PHP. LAMP stack makes it easy to build dynamic websites and application and host a wide range of web services. 

In this guide, you will install the LAMP stack on a CentOS-7 server.

### Step 1: Install Apache

On CentOS, Apache is identified by the https package. To install the web server, we need to update the system, then attempt to install httpd.

Update the server
```
yum update 
```

Install Apache with the **`httpd`** package.

```
yum install httpd -y
```

Once installed, start the Apache daemon and enable it to start automatically during system boot.
 ```
 systemctl start httpd
 systemctl enable httpd
 ```
If firewall enabled, you must open the http and https transport port for the web server to function.

```
firewall-cmd --permanent --zone=public --add-service=http

firewall-cmd --permanent --zone=public --add-service=https

systemctl reload firewalld

```

Now, test the web server's pubic IP address in a browser. You should see the Apache test 123 page but sometimes I hate to see it :-)

### Step 2: Add MariaDB Yum repository

On Centos 7, MySQL is substituted by MariaDB.

Find the right version of repository and install it under `/etc/yum.repos.d`

Run the following commands to add the repository provided by Mariadb to your CentOS server.

``` 
curl -LsS -Ohttps://downloads.mariadb.com/MariaDB/mariadb_repo_setup
```

```
bash mariadb_repo_setup --mariadb-server-version=10.5
```

After installation check it out below
```
ls /ect/yum.repos.d
```
there are 2 new files are added `mariadb.repo` `mariadb_repo_setup`

Confirm the epository is working by updateing cache

```
yum makecache
```

Check the list of available repository and confirm it

```
yum repolist
```

Now MariaDB package is ready to install

### Step-3 Install MySQL (MariaDB)

```
yum install MariaDB-server MariaDB-clint MariaDB-backup
```

Start MariaDB server
```
systemctl start mariadb
systemctl enable mariadb
```
### Step-4

```
sudo mariadb-secure-installation
```
Y
Y
Y
Y
Y

After installation login with root password
```
mysql - root -p
```
```
SELECT VERSION ();
```
```
SHOW SATABASE();
```

Order to connect from wordpress server to database server we have to have database and user that able to get information from the database.

#### Creating database

CREATE DATABASE name of the database

``` CREATE DATABASE class;```

#### Create user account:
CREATE USER 'createusername'@'IP address for wordpress server' IDENTIFIED BY'createpassword'

```
CREATE USER 'bob'@'IPaddress'IDENTIFIED BY'bobs password'
```

### Step-3:Grant Privileges on a Database in MySQL

```
GRANT ALL PRIVILEGES ON database_name.* TO 'database_user'@'localhost';
```

PLUSH PRIVILEGES;

How to login Database from Wordpress server:
```
mysql -h DB-IP address -u username -p
```