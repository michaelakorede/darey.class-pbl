
## MEAN STACK IMPLEMENTATION 

#### STEP ONE: Mean Stack Deployment to Ubuntu in AWS

> sudo apt update

> sudo apt upgrade

Add certificates

> sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates

![add certification](https://user-images.githubusercontent.com/83889926/158484278-c4b4301c-27b5-40be-aa34-de33bdb2295f.PNG)

> curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

Way 1: Install Install Node.Js

> sudo apt-get install -y nodejs

![Installed nodejs](https://user-images.githubusercontent.com/83889926/158484329-a3eb1c3c-b559-4bbe-87af-f98eadc1c49a.PNG)

Way 2: Install MongoDB

> sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

> echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list


Install MongoDB

> sudo apt install -y mongodb

Start The server

sudo systemctl status mongodb

> Install npm – Node package manager.

> sudo apt install -y npm

Install body-parser package

NOTE: We need ‘body-parser’ package to help us process JSON files passed in requests to the server.

sudo npm install body-parser: Create a folder named ‘Books’

> mkdir Books && cd Books
In the Books directory, Initialize npm project

> npm init

Add a file to it named server.js

> vi server.js
Copy and paste the web server code () into the server.js file.

#### STEP TWO: Install Express and Set up routes to the Server

Way 3: Install Express and set up routes to the server

Note: Express is a minimal and flexible Node.js web application framework that provides features for web and mobile applications.

Note: We also will use Mongoose package which provides a straight-forward, schema-based solution to model your application data.

> sudo npm install express mongoose

In ‘Books’ folder, create a folder named apps

> mkdir apps && cd apps

Create a file named routes.js

> vi routes.js

Copy and paste the code..() into routes.js

In the ‘apps’ folder, create a folder named models

> mkdir models && cd models

Create a file named book.js

> vi book.js

Copy and paste the code ..() into ‘book.js’

Way 4 – Access the routes with AngularJS

Change the directory back to ‘Books’
cd ../..

Create a folder named public

> mkdir public && cd public

Add a file named script.js

> vi script.js

Copy and paste the Code ..() (controller configuration defined) into the script.js file.

In public folder, create a file named index.html;

> vi index.html

Copy and paste the code..() into index.html file.

Change the directory back up to Books

> cd ..

Start the server by running this command:

>> node server.js

| If server is now up and running, we can connect it via port 3300|

> curl -s http://localhost:3300

Note: ***you need to open TCP port 3300 in your AWS Web Console for your EC2 Instance.

Now you can access our Book Register web application from the Internet with a browser using Public IP address or Public DNS name.

![Web Book Register Application](https://user-images.githubusercontent.com/83889926/158486131-6b130561-97c3-4eda-bad3-62d1271e32c3.PNG)




