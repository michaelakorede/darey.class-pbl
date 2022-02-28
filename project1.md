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


