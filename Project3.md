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




## MEARN STACK IMPLEMENTATION

#### STEP ONE: Beckend configuration

> sudo apt-get update

> sudo apt upgrade

{Install Node.js}

> sudo apt-get install -y nodejs
![installed nodejs](https://user-images.githubusercontent.com/83889926/158443478-cea9607f-a0ef-4fbb-bb48-0e2aa1152052.PNG)

{Application code Setup} 

> Mkdir Todo 

> (Change the directory to Todo) 

>cd Todo

Initialise my project to create a new file package.json

> npm init

Install Expressjs

Note: install using npm

> npm install express

![installed expressjs](https://user-images.githubusercontent.com/83889926/158444046-2ddb49f4-0b4a-4854-ba3a-09a01e62b839.PNG)

Note: Create a file index.js

>touch index.js

Open the index.js and type the code and saved

>vim index.js

Note: We have specified to use port 5000 in the code and we need to open this port in EC2 Security Groups.
..Now it is time to start the server to see if it works. 

>node index.js

![server runing on browser](https://user-images.githubusercontent.com/83889926/158446762-dff38fc2-8113-40d2-b8ff-24b210103ac1.PNG)

We need to create routes that will define various endpoints that the To-do app 
>mkdir routes
Change directory to routes folder.
cd routes
Now, create a file api.js with the command below
touch api.js
Open the file with the command below
vim api.js
Copy below code in the file()

Next: we create Models directory 
Change directory back Todo folder with cd .. and install Mongoose

>npm install mongoose
![installed mongoose](https://user-images.githubusercontent.com/83889926/158447913-9a30378c-8de6-41f9-a943-0e82835ef8dc.PNG)

Create a new folder models (mkdir models - cd models - touch todo.js)

>mkdir models && cd models && touch todo.js

|Open the file created with vim todo.js then paste the code..()

Now we need to update our routes from the file api.js in ‘routes’ directory to make use of the new model.
In Routes directory, open api.js with vim api.js, delete the code..() inside with :%d command and paste new code ..()

###### My MongoDB database was created suuccessfully. 
![Database connected successfully](https://user-images.githubusercontent.com/83889926/158448994-af03c04b-b784-46e7-8a96-7d87e09e2e63.PNG)

##### Testing Backend Code without Frontend using RESTful API: POSTMAN
Create POST 
![POST](https://user-images.githubusercontent.com/83889926/158449328-aa8473a5-2a32-4933-a048-d48d2bd9807d.PNG)
Create GET
![GET](https://user-images.githubusercontent.com/83889926/158449434-aca98c96-0d05-4baa-adf5-9d0a2de27be5.PNG)


### STEP TWO: FRONTEND CREATION
Create User Interface for web  clinet 

Todo Directory , Run >npx create-react-app client. This will create a new folder in your Todo directory called client.
Running a React App
Before testing the react app, there are some dependencies that need to be installed.

Install concurrently and nodemon
>npm install concurrently --save-dev
Install nodemon. 
>npm install nodemon --save-dev
In Todo folder open the package.json file. Change the highlighted part of the below screenshot..() and replace with the code..()

Configure Proxy in package.json

cd client
Open the package.json file
vi package.json
Add the key value pair in the package.json file "proxy": "http://localhost:5000".

Todo directory, and simply do:

>npm run dev

Your app should open and start running on localhost:3000
![Run on Port 3000](https://user-images.githubusercontent.com/83889926/158450689-59cbc044-b2a9-4f7c-ac24-2dcf63c99710.PNG)

###### Creating your React Components

>cd client & cd src & mkdir components

>cd components

Inside ‘components’ directory create three files Input.js, ListTodo.js and Todo.js.

Open Input.js file

vi Input.js

Copy and paste the following code ..()

###### To make use of Axios, which is a Promise based HTTP client for the browser and node.js
Move to the src folder

cd ..Move to clients folder: cd ..Install Axios: npm install axios

Go to ‘components’ directory: cd src/components
After that open your ListTodo.js

>vi ListTodo.js

in the ListTodo.js copy and paste the following code..()
Then in your Todo.js file you write the following code..()

Adjust our react code. Delete the logo and adjust our App.js.
Move to the src folder: cd ..
Make sure that you are in the src folder and run

>vi App.js

>Copy and paste the code..()

>vi App.css

Then paste the following code..() into App.css:

In the src directory open the index.css

>vim index.css

Copy and paste the code..() 

Go to the Todo directory

>cd ../..

run:

>npm run dev

![React app](https://user-images.githubusercontent.com/83889926/158452739-4ee4654f-08dc-4716-8937-dcdb5d80f313.PNG)
