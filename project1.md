## WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS

###### STEP ONE: Installing apache and updating the firewall

##### APACHE

*The Apache web server is among the most popular web servers in the world. Has an active community of users, 
and has been in wide use for much of the history of the web, which makes it a great default choice for hosting a website.
However Apache HTTP Server is the most widely used web server software.  Apache is an open source software available for free. It runs on 67% of all webservers in the world --fast, reliable, and secure:  Websites and other applications can run on other web server software as well. Such as Nginx, Microsoft’s IIS, etc*.

| Install Apache using Ubuntu’s |

> update a list of packages in package manager
run: sudo apt-get update 

![apt-get update](https://user-images.githubusercontent.com/83889926/156071136-af50a1b7-4ca9-4b2b-8f8f-941bc91f8505.PNG)


> run apache2 package installation
run: sudo apt-get install apache2

![install apache2 successfully](https://user-images.githubusercontent.com/83889926/156071183-6fcb7691-7140-44da-a822-a6567d392635.PNG)

To verify that apache2 is running as a Service in my OS

> sudo systemctl status apache2

![verify that apache2 is running as a Service in our OS](https://user-images.githubusercontent.com/83889926/156071032-9d8e2a76-d05f-47f4-bc1e-1563a3508e64.PNG)


| Let us try to check how we can access it locally in our Ubuntu shell, run | 

 > curl http://localhost:80
or
 > curl http://127.0.0.1:80


![Able to access it locally on Ubuntu shell](https://user-images.githubusercontent.com/83889926/156071505-758da4ee-043c-44a5-8812-f72a18050921.PNG)

*NOTE* 

Now it is time for us to test how our Apache HTTP server can respond to requests from the Internet.
From the web browser of your choice and try to access following url

http://3.142.239.5:80; However it is possible for the server to be down 'IF' the server is shut down. 

![Apache 2 Ubuntu run successfully](https://user-images.githubusercontent.com/83889926/156071979-ff3f8b6f-edda-476e-aa9e-ae57208d86f0.PNG)


###### STEP TWO: INSTALLING MYSQL

We need to install a Database Management System (DBMS) to be able to store and manage data for the site created in a relational database. MySQL is a popular relational database management system used within PHP environments.

Again, use ‘apt’ to acquire and install this software:

> sudo ap-get install mysql-server

When prompted, confirm installation by typing Y, and then ENTER.

When the installation is finished, it’s recommended that you run a security script that comes pre-installed with MySQL. This script will remove some insecure default settings and lock down access to your database system. Start the interactive script by running:

> sudo mysql_secure_installation

This will ask if you want to configure the VALIDATE PASSWORD PLUGIN.

Answer Y for yes, or anything else to continue without enabling.

NOTE: Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : y
For the rest of the questions, press Y and hit the ENTER key at each prompt. This will remove some anonymous users and the test database, disable remote root logins, and load these new rules so that MySQL immediately respects the changes you have made.

When you’re finished, test if you’re able to log in to the MySQL console by typing:

> sudo mysql
This will connect to the MySQL server as the administrative database user root, which is inferred by the use of sudo when running this command. You should see output like this:

Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 11
Server version: 8.0.22-0ubuntu0.20.04.3 (Ubuntu)
Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.
Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.


![install mysql successfully](https://user-images.githubusercontent.com/83889926/156073216-c7eb6a00-8561-4ad1-86b6-51c2fa34f153.PNG)



Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

> mysql> 
To exit the MySQL console, type:

> mysql> exit

STEP THREE:  INSTALLING PHP

