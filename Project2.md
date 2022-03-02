## WEB STACK IMPLEMENTATION (LEMP STACK)

#### STEP ONE: Installing the Nginx Web Server

| Nginx installed |

> sudo apt-get update
> sudo apt-get install nginx

Nginx web server is active and running on Ubuntu 20.04 server.

![connect to instance through ssh and update](https://user-images.githubusercontent.com/83889926/156261540-4b347a6b-7849-4019-b13a-668c2e051f61.PNG)

nginx was successfully installed and is running as a service in Ubuntu, run:

> sudo systemctl status nginx

![install nginx successfully](https://user-images.githubusercontent.com/83889926/156261997-773a61f3-176a-428f-af51-008d01931c1b.PNG)

The server is running and we can access it locally and from the Internet: We can access it locally in our Ubuntu shell, run:

curl http://18.222.230.79:80 

![Nginx server respond](https://user-images.githubusercontent.com/83889926/156262684-0a52584d-b5ea-41e4-9cbc-73fa0f4fb98f.PNG)

### STEP TWO: INSTALLING MYSQL

We need to install a Database Management System (DBMS) to be able to store and manage data for our site in a relational database. 

> sudo apt-get install mysql-server

When prompted, confirm installation by typing Y, and then ENTER.

When the installation is finished, it’s recommended that you run a security script that comes pre-installed with MySQL. T

> sudo mysql_secure_installation

![security script that comes pre-installed with MySQL](https://user-images.githubusercontent.com/83889926/156263548-ff762a1b-b182-4495-a33b-85d38caaf4ee.PNG)

## When you’re finished, test if you’re able to log in to the MySQL console by typing:

![Login to MySQL](https://user-images.githubusercontent.com/83889926/156263612-0aba5a3a-df02-4c14-ada3-34f42c5d558b.PNG)

> sudo mysql

![MYSQL Installed](https://user-images.githubusercontent.com/83889926/156263835-f1b1b6a5-6910-485c-b9ac-0d5c57c3f6ca.PNG)

> mysql> 
To exit the MySQL console, type:
> mysql> exit


### STEP THREE:  INSTALLING PHP

*PHP is the component of our setup that will process code to display dynamic content to the end user*

To install these 2 packages at once, run:

> sudo apt-get install php-fpm php-mysql
Once the installation is finished, 

You now have your PHP components installed

### STEP FOUR:  CONFIGURING NGINX TO USE PHP PROCESSOR

NOTE: On Ubuntu 20.04, Nginx has one server block enabled by default and is configured to serve documents out of a directory at /var/www/html.

Create the root web directory for your_domain as follows:

> sudo mkdir /var/www/projectLEMP

 Let assign ownership of the directory with the $USER environment variable, which will reference our current system user:

> sudo chown -R $USER:$USER /var/www/projectLEMP

Then we open a new configuration file in Nginx’s sites-available directory using our preferred command-line editor. Here, we’ll use nano:

> sudo nano /etc/nginx/sites-available/projectLEMP

Paste in the following bare-bones configuration:

#/etc/nginx/sites-available/projectLEMP

*server {
    listen 80;
    server_name projectLEMP www.projectLEMP;
    root /var/www/projectLEMP;

    index index.html index.htm index.php;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
     }

    location ~ /\.ht {
        deny all;
    }

}*

If you’re using nano, typing CTRL+X and then y and ENTER to confirm.

linking to the config file from Nginx’s sites-enabled directory:

> sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/

> sudo nginx -t
|You shall see following message:|

**nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful**

Note: We also need to disable default Nginx host that is currently configured to listen on port 80, for this run:

> sudo unlink /etc/nginx/sites-enabled/default

> sudo systemctl reload nginx

**Your new website is now active, but the web root /var/www/projectLEMP is still empty. Create an index.html file in that location so that we can test that your new server block works as expected:**

> sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html

Now go to your browser and try to open your website URL using IP address:

http://18.222.230.79:80

![Create an index html file in that location so that we can test that your new server block](https://user-images.githubusercontent.com/83889926/156265752-0aabcaef-5600-4d2c-bf8b-cc5c21fc1d41.PNG)

### STEP FIVE: TESTING PHP WITH NGINX
Open a new file called info.php within our document root in our text editor:

> sudo nano /var/www/projectLEMP/info.php

Type or paste the following above lines into the new file. 

<?php
phpinfo();

You can now access this page in our web browser by visiting the domain name or public IP address we’ve set up in our Nginx configuration file, followed by /info.php:

However, I'm using IP 
> http://18.222.230.79/info.php

![TESTED PHP WITH NGINX](https://user-images.githubusercontent.com/83889926/156266656-769aab56-51db-43a5-a7c8-c60e5841324d.PNG)


### STEP SIX: RETRIEVING DATA FROM MYSQL DATABASE WITH PHP (CONTINUED)

> sudo mysql

![connect to the MySQL](https://user-images.githubusercontent.com/83889926/156267239-86f009c6-04fa-494c-ad59-a8a5ff998b29.PNG)

> mysql> SHOW DATABASES;

![Show Database](https://user-images.githubusercontent.com/83889926/156267956-7bcfcd03-970a-49fd-8aa1-36d48825fbb4.PNG)

> mysql>  SELECT * FROM example_database.todo_list;

![Data was successfully saved on table](https://user-images.githubusercontent.com/83889926/156268327-6334a399-fb63-4ff7-a4b4-f926c577fe55.PNG)

Let's create a PHP script that will connect to MySQL and query for your content. 

> nano /var/www/projectLEMP/todo_list.php

Copy this content into your todo_list.php script:

We Saved and closed the file when you are done editing.

http://18.222.230.79/todo_list.php

![Page for the content inserted](https://user-images.githubusercontent.com/83889926/156269249-4aadc92f-6e87-4026-a909-10acd56fa12d.PNG)


