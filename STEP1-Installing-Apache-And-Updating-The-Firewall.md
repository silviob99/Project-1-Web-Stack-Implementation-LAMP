![LAMP-Banner](https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/1d34113d-d252-47a3-b73a-c852567090a8)


What exactly is Apache?

[Apache HTTP Server](https://httpd.apache.org/) is the most widely used web server software. Developed and maintained by Apache Software Foundation. Apache is an open source software available for free. It runs on 67% of all webservers in the world. It is fast, reliable, and secure. It can be highly customised to meet needs of many different environments by using extensions and modules. Most WordPress hosting providers use Apache as their web server 
software. However, websites and other applications can run on other web server software as well. Such as [Nginx](https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/), [Microsoft IIS](https://learn.microsoft.com/en-gb/iis/get-started/introduction-to-iis/introduction-to-iis-architecture), etc.

The Apache web server is among the most popular web servers in the world. It's well documented, has an active community of users, and has been in wide use for much of the history of the web, which makes it a great default choice for hosting a website. 
Install Apache using Ubuntu's package manager ['apt'](https://ubuntu.com/server/docs/package-management)

```
#update a list of packages in package manager
sudo apt update

#run apache2 package installation
sudo apt install apache2
```

<img width="960" alt="SSH apt-update" src="https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/4afefaaf-4020-4ec1-b365-fc1fcac85a2c">


To verify that apache2 is running as a Service in our OS use following command

```
sudo systemctl status apache2
```

If it's green and running, then you did everything correctly-you have just launched your first Web Server in the Cloud!
  
<img width="960" alt="SSH sudo-status" src="https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/ebc1bd57-1ee8-4d98-8ea7-1c8ba88c0698">  



Before we can receive any traffic by our Web Server, we need to open TCP port 80 which is the default port that web browsers use to access web pages on the internet.
As we know, we have TCP port 22 open by default on our EC2 machine to access it via SSH, so we need to add rule to EC2 configuration to open inbound connection through port 80:  

<img width="960" alt="AddInboundRule06-07" src="https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/9b901155-8a61-45bc-a097-deb8b3c4e0d7">  


[![Edit inbound rules](<img width="960" alt="AddInboundRule06-07" src="https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/f92cbf5b-1bb2-425e-88ca-ea438b9684ba">)](https://youtu.be/-4F5iYKVkLg)


