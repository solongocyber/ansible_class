
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