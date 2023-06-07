![LAMP-Banner](https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/2e2fc16a-8345-4a74-9383-4bebc4ab49bd)

Now that we have web server up and running, you need to install a [Database Management System (DBMS)](https://www.javatpoint.com/dbms-tutorial) to be able to store and
manage data for your site in a [Relational Database](https://aws.amazon.com/relational-database/). [MySQL](https://www.mysql.com/) is a popular relational database management system used within PHP environments, so I will use it in my project.  

Again I will use 'apt' to acquire and install this software. 

```sudo apt install mysql-server```  

When prompted, confirm installation by typing **Y** and then **ENTER**.  
When the installation is finished, it's reommended that you run a security script that comes pre-installed with MySQL. This script will remove some insecure default settings and lock down access to your database system. Start interactive script by running 

```sudo mysql_secure_installation```  

This will ask you if you want to configure the **VALIDATE PASSWORD  PLUGIN**.  

**Note** Enabling this feature is something of a judgment call. If enabled, passwords which don't match the specified criteria will be rejected by MySQL with an error.  
It is safe to leave validation disabled, but you should always use strong unique passwords for database credentials.  








