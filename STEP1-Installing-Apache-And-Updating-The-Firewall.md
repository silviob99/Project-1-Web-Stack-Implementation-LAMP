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



Before we can receive any traffic by our Web Server, we need to open TCP port 80, which is the default port that web browsers use to access web pages on the internet.

As we know, we have TCP port 22 open by default on our EC2 machine to access it via SSH, so we need to add a rule to the EC2 configuration to open an inbound connection through port 80.

[Edit Inbound Rules<img width="960" alt="AddInboundRule06-07" src="https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/06e9b819-f304-422d-8231-5c9a577c2082">](https://youtu.be/-4F5iYKVkLg)

Our server is running and we can access it locally and from the internet (Source 0.0.0.0/0 means 'from any IP address').  

First let us try to check how we can access it locally in our Ubuntu shell, run:
```
curl http://localhost:80
or 
curl http://127.0.0.1:80  
```  

These two commands above actually do pretty much the same - they use '**_curl_**' command to request our Apache HTTP Server on port 80  
(actually you can even try not to specify any port-it will work anyway). The difference is that in the first case we try to access  our 
server via [DNS Name](https://aws.amazon.com/route53/what-is-dns/) and in the second one - by IP address (in this case IP address 127.0.0.1 corresponds to DNS name 'localhost' and the
process of converting a DNS name to IP address is called "resolution").   

As an output you can see some strangely formatted test, do not worry, we just made sure that our Apache web service responds to 'curl'
command with some payload.  

Now we have to test how our Apache HTTP server can respond to requests from the Internet.  
Open a web browser of your choice and try to access following url  

```http://<Public-IP-Address>:80```  

Another way to retrieve your Public IP address, other than to check it in AWS Web console, is to use following command:  

```curl -s http://169.254.169.254/latest/meta-data/public-ipv4```  

The URL in browser shall also work if you do not specify port number since all web browsers use port 80 by default.  
If you see following page, then your web server is now correctly installed and accessible through your firewall.  

<img width="960" alt="Apache" src="https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/c0c8e4bb-55fd-4129-85b3-f0c0bf6a5fb3">  












