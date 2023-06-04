![LAMP-Banner](https://github.com/silviob99/DevOps-Projects-1/assets/107585020/b1ca421d-2798-4d1e-b7da-3d9b4b9cdbd9)

### What is a tehnology stack?

A technology stack is a set of frameworks and tools used to develop a software product. This set of frameworks and tools are very specifically chosen to work together in creating a well-functioning software. They are acronymns for individual technologies used together for a specific technology product some examples are:  

###### LAMP (Linux, Apache, MySQL, PHP, Python or Perl)  
###### LEMP (Linux, Nginx, MySQL, PHP)  
###### MERN (MongoDB, ExpressJS, ReactJS, NodeJS)  
###### MEAN (MongoDB, ExpressJS, AngularJS, NodeJS)  

#### Step 0- Preparing prerequisits
In order to complete this project I will need AWS account and a virtual server with Ubuntu Server OS.
AWS is the biggest Cloud Server Provider and it offers free tier account that we I'm going to leverage for my projects.  
AWS can provide free virtual servers  
1. [AWS account setup](https://youtu.be/XhW17g73fvY)
<img width="960" alt="LAMP-AWSFreeTier" src="https://github.com/silviob99/DevOps-Projects-1/assets/107585020/b1bc83d3-d27e-4d6c-bc02-803b52a5195e">  

2. [Creating your EC2 instance](https://youtu.be/a8CBE_WN7rA)  
<img width="960" alt="LAMP-Picture1" src="https://github.com/silviob99/DevOps-Projects-1/assets/107585020/708fd556-1efb-4d36-b258-dc6b31887bb7">  

###### **IMPORTANT** -save your private key(.pem file) and do not share it with anyone! If you lose it, you will not be able to connect to your server ever again.

1. For Windows users you will need a tool called **putty** to connect to your EC2 instance. Download **putty** [Here]([path/to/file](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)) 
2. For Mac users, you can simply open up **Terminal** and use the **ssh** command to get into the server. 

###### IMPORTANT NOTICE  
Both **Putty** and **ssh** use the **SSH protocol** to establish connectivity between computers. It is the most secure protocol because it uses crypto algorithms to encrypt the data that is transmitted-it uses TCP port **22** which is open for all the newly created EC2 instances in AWS by default.

The process to connect to the virtual server is different between Windows and Mac. So lets take a quick tour:

#### [Connecting to EC2 using the terminal on Mac/Linux](https://www.youtube.com/watch?v=8UqtMcX_kg0&ab_channel=StephaneMaarek)
#### [Connecting to EC2 using Putty](https://www.youtube.com/watch?v=051Jdka8piY&ab_channel=AWSMadeEasy)

###### IMPORTANT 
Anywhere you see these anchor tags <>, going forward, it means you will need to replace the content in there with values specific to your situation. For example, if you need to replace the path where you have saved the private key on your machine, I will write something like **<private-key-name>.**  

If the private key you downloaded was named **my-private-key.pem** simply remove the anchor tags and insert **my-private-key.pem** in the command you are required to execute. 
Let's try this and follow the instructions below to get some work done. 
- Change permissions to the private key file (.pem), otherwise you can get an error "Bad permissions"

```sudo chmod 0400 <private-key-name>.pem```
- Connect to the instance by running  

```ssh -i <private-key-name>.pem ubuntu@<Public-IP-address>```

 Congratulations! You have just created your very first Linux Server in the Cloud and our set up looks like this now. (You are the client)
 
![SSH-into-instance](https://github.com/silviob99/DevOps-Projects-1/assets/107585020/66cc0455-f975-4664-bd15-c3ac9ba30008)

Please read information about AWS free tier limits and make sure that you *STOP* your EC2 instance when you are not using it.

 <img width="766" alt="LAMP-Picture2(stop-inst)2023-06-04" src="https://github.com/silviob99/DevOps-Projects-1/assets/107585020/993ff1fa-5e41-4dd5-9d78-fa2151f66e6a">

All we need to know right now is that we can use 750 hours (31.25 days) of t2.micro server per month for the first 12 months **FOR FREE**.

You can launch and stop new instances when you need to, but by default there is a soft-limit of maximum 5 running instances at the same time. In my first project I will be using only 1 running instance at a time. When you stop an instance - it stops consuming available hours. 

Note that every time you stop and start your EC2 instance - you will have a **new IP address**. It is normal behavior, so do not forget to update your SSH credentials when you try to connect to your EC2 server. 

Let us move on and configure our EC2 machine to serve a Web server.





 
   











