# WEB SERVER  
From this repository you can get basic config, for one of most popular web server - nginx.

## Getting Started
These instructions will get you a copy of the project up and running on your local machine web server

### Prerequisites

What things you need to install the software and how to install them

For debian and ubuntu:
```
apt update
apt install nginx 
systemctl start nginx
```

### Notes

If nginx fails.
In default, nginx use port 80, but there are many programs that use it as their default port, for example apache.
Find out if other program use port 80
```
netstat -tunlp | grep 80
```
If it is true, you can:
+ stop other program
```
systemctl stop other_program
```
+ change  port 80 to other port ( for example 81 ) in nginx configuration files 
```
egrep -r "listen.*80;" /etc/nginx
```
## Deployment
Clone repository and copy nginx.conf to /etc/nginx
```
cd /tmp
git clone git@gitlab.rebrainme.com:mail.alexandr.vovk.v/rebrain-devops-task-checkout.git
cp /tmp/rebrain-devops-task-checkout/nginx.conf /etc/nginx/
```
## Run configuration test
```
nginx -t
```

## Run web server with new config
```
nginx -s reload
```

## Authors
+ Alexandr Vovk - Initial work - [GITHUB](https://github.com/AlexandrVovk) 

