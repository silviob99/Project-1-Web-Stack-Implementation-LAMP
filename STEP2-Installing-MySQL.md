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

Answer *Y* for yes, or anything else to continue without enabling. 

```VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password 
and allows the users  to set only those passwords which are 
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No:
```
If you answer 'yes' you'll be asked to select a level of password validation. Keep in mind that if you enter **2** for the strongest level, you will receive 
errors when attempting to set any password which does not contain numbers, upper and lowercase letters, and special characters, or which is based on common dictionary
words. 

```
There are three levels of password validation policy:

LOW     Length >= 8
MEDIUM  Length >= 8, numeric, mixed case, and special characters 
STRONG  Length >= 8, numeric, mixed case, special characters and dictionary         file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 1
```

Regardless of whether you chose to set up the VALIDATE PASSWORD PLUGIN, your server will next ask you to select and confirm a password for the MySQL **root** user.  
This is not to be confused with the **system root**. The **database root** user is an administrative user with full privileges over the database system. Even though
the default authentication method for the MySQL root user dispenses the use of a password, **even when one is set**, you should define a strong password here as an
additional safety measure. I'll talk about this later.  

If you enabled password validation, you'll be shown the password strength for the root password you just  entered and your server will ask if you want to continue  
with that password. If you are happy with your current password, enter **y** for 'yes' at the prompt. 






