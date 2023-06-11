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
</Virtual Host>
```
To save and close the file, simply follow the steps below:  

1.Hit the **esc** button on the keyboard 
