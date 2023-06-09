![LAMP-Banner](https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/21c04ed6-3fba-4d45-b567-e4c9abfa2351)


In this step I will set up domain called _**sbanfic-projectlamp**_, but we can replace it with any other domain. 
Apache on Ubuntu 20.04 has one server block enabled by default that is configured to serve documents from the **/var/www/html** directory.
We will leave this configuration as is and will add our own directory next to the default one.
Create the directory for _**sbanfic-projectlamp**_ using **mkdir** command as follows.  
```sudo mkdir /var/www/sbanfic-projectlamp ``` 

Next, assign ownership of the directory with your current system user:  
```sudo chown -R $USER:$USER /var/www/sbanfic-projectlamp``` 

Then create and open a new configuration file in Apache's **sites-available** directory using your prefered command-line editor. Here, we'll be
using **vi** or **vim** (They are the same):  
```sudo vi /etc/apache2/sites-available/projectlamp.conf```  

This will create new blank file. Paste it in the following bare-bones configuration by hitting on **i** on the keyboard to enter the insert mode,  
and paste the text:  



```
<VirtualHost *:80>
    ServerName sbanfic-projectlamp
    ServerAlias www.sbanfic-projectlamp
    ServerAdmin webmaster@localhost  
    DocumentRoot  /var/www/sbanfic-projectlamp  
    ErrorLog ${APACHE_LOG_DIR}/error.log  
    CustomLog ${APACHE_LOG_DIR}/access.log combined 
</VirtualHost>
```
To save and close the file, simply follow the steps below:  

1. Hit the **esc** button on the keyboard 
2. Type **:**
3. Type **wqa!** (w for write and q for quit)
4. Hit ENTER to save the file 

You can use the ls command to show the new file in the **sites-available** directory  
```sudo ls /etc/apache2/sites-available``` 

You will see sonething like this  
```000.default.conf default-ssl.conf sbanfic-projectlamp.conf```  

With this VirtualHost configuration, we're telling Apache to serve **sbanfic-projectlamp** using **/var/www/sbanfic-projectlamp** as it's root directory. If you would like to test Apache without domain name, you can remove or comment out the options ServerName and ServerAlias by adding a **#** character in the beginning of each option's lines. Adding the **#** character there will tell the program to skip processing the instructions on those lines.  

You can now use **a2ensite** command to enable the new virtual host.   

```sudo a2dissite 000-default```  

To make sure your configuration file doesn't contain syntax errors, run:  

```sudo apache2ctl configtest```  

Finally, reload Apache so these changes take effect:  

```sudo systemctl reload apache2```  

Your new website is now active but the web root **/var/www/sbanfic-projectlamp** is still empty. Create an index.html file in that location so that we can test that the virtual host works as expected:  

```  
echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) | sudo tee /var/www/sbanfic-projectlamp/index.html
```  

Now go to your browser and try  to open your website URL using IP address:  

```http://<Public-IP-Address>:80```  

If you see the text from **'echo'** command you wrote to index.html file, then it means your Apache virtual host is working as expected.  
In the output you will see your server's public hostname (DNS name) and public IP address. You can also access your website in your browser by public DNS name, not only by  IP - try it out, the result, the result must be the same (port is optional)  

```http://<Public-DNS-Name>:80```  

You can leave this file in place as a temporary landing page for your application until you set up an **index.php** file to replace it. Once you do that, remember to remove or rename the **index.html** file from your document root, as it would take precedence over an **index.php** file by default.  

