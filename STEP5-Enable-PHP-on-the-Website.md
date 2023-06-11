![LAMP-Banner](https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/f3d68555-32fa-40e3-bb8c-b066557221d8)

With the default **Directoryindex** settings on Apache, a file named **index.html** will always take precedence over an **index.php** file. This is 
useful for setting up maintenance pages in PHP applications, by creating temporary **index.html** file containing an informative message to visitors. 
Because this page will take precedence over **index.php** page, it will then become the landing page for the application. Once maintenance is over, the 
**index.html** file is renamed or removed from the document root, bringing back the regular application page. 

In case you want to change this behavior, you'll need to edit the **etc/apache2/mods-enabled/dir-conf** file and change the order in which the **index.php**
file is listed within the **Directoryindex** directive:  

```sudo vim /etc/apache2/mods-enabled/dir.conf```  

```  
<IfModule mod_dir.c>
        #Change this:  
        #DirectoryIndex index.html index.cgi index.pl index.php index.xhtml index.htm 
        #To this:  
        DirectoryIndex index.php index.html index.cgi index.pl index.xhtml index. htm  
</IfModule>
```

After saving and closing the file, you will need to reload Apache so the changes take effect:  

```sudo systemctl reload apache2```  

Finally, we will create a PHP script to test that PHP is correctly installed and configured on your server.  
Now that you have a custom location to host your website's files and folders, we'll create a PHP test script to confirm that Apache is able
to handle and process requests for PHP files. 
Create a new file named **index.php** inside your custom web root folder. 

```vim /var/www/sbanfic-projectlamp/index.php```

This will open a blank file. Add the following text, which is valid PHP code, inside the file:  

```
<?php
phpinfo();
```  

When you are finsihed, save and close the file, refresh the page and you will see a page similar to this:  

<img width="960" alt="PHPversion(homepage)" src="https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/b4e8b14f-f8a2-46e4-9660-458ae029b20e">

This page provides information about your server from the perspective of PHP. It is useful for debugging and to ensure that your settings are being applied correctly.  

If you can see this page in your browser, then your PHP installation is working as expected.  
After checking the relevant information about your PHP server through that page, it's best to remove the file you created as it contains
sensitive information about your PHP environment -and your Ubuntu server. You can use **rm** to do so:  

```sudo rm/var/www/projectlamp/index.php```
