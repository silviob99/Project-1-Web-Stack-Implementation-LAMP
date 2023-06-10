![LAMP-Banner](https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/85f7de03-c927-433d-b41d-336943041bee)


You have Apache installed to serve your content and MySQL installed to store and manage your data. PHP is the component of our setup that will process code to display dynamic content to the end user. In addition to the _**php**_ package, you'll need _**php-mysql**_, a PHP module that allows PHP to communicate with MySQL-based databases. You'll also need _**libapache2-mod-php**_ to enable Apache to handle PHP files. Core PHP packages will automatically be installed as dependencies.  
 
To install these 3 packages at once, run:  

```sudo apt install php libapache2-mod-php php-mysql```  

Once this installation is finished, you can run the following command to confirm your PHP version:

```php -v```  
```
PHP 8.1.2-1ubuntu2.11 (cli) (built: Feb 22 2023 22:56:18) (NTS)
Copyright (c) The PHP Group 
Zend Engine v4.1.2, Copyright (c) Zeno Technologies 
    with Zend OPcache v8.1.2-1ubuntu2.11, Copyright (c), by Zend Technologies 
```  

At this point, your LAMP stack is completely installed and fully operational.

- [x] **L**inux
- [x] **A**pache
- [x] **M**ySQL
- [x] **P**HP  

To test your setup with PHP script, it's best to set up proper Apache Virtual Host to hold your website's files and folders. Virtual host allows you to have multiple websites located on a single machine and users of the websites will not even notice it.  

![ApacheVirtualHost](https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/f0bf706a-5983-4b91-9be7-917fee59ba18)

