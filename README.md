![LAMP-Banner](https://github.com/silviob99/Project-1-Web-Stack-Implementation-LAMP/assets/107585020/4be6fc17-c488-461c-a6a7-ea9a68f570b5)

# Project-1-LAMP (Linux, Apache, MySQL, PHP) Web Stack Implementation
This project provides a step-by-step guide on setting up a LAMP (Linux, Apache, MySQL, PHP) web stack on an Ubuntu 20.04 server.

## Table of Contents  
-Project Overview
-Installation
-Usage
-Steps


### Project Overview
Project-1: Web Stack Implementation (LAMP) is a tutorial-based project that guides users through the process of setting up a LAMP (Linux, Apache, MySQL, PHP) web stack on Ubuntu 20.04. The project aims to provide a step-by-step guide for beginners to learn how to install and configure the essential components of a web server.

### Prerequisites
Before starting the installation process, ensure that you have the following prerequisites:

Ubuntu 20.04 server
SSH access to the server
Basic knowledge of Linux command line

### Installation  

To install and set up the LAMP stack on Ubuntu 20.04, follow these steps:

-Set up an Ubuntu 20.04 server.
-Update the system and install necessary packages.
-Install and configure Apache.
-Install and secure MySQL.
-Install and configure PHP. 

### Usage 

Once the LAMP stack is set up, you can use it to host and run web applications. To test if your installation is successful, you can access the Apache default page or create your own web page. 

### Steps  

Step 1: Set Up Ubuntu 20.04
Step 2: Update System and Install Packages
Step 3: Install and Configure Apache
Step 4: Install and Secure MySQL
Step 5: Install and Configure PHP 

### Testing the Setup

Create an index.html file for testing:  
```echo 'Hello LAMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) | sudo tee /var/www/sbanfic-projectlamp/index.html```


