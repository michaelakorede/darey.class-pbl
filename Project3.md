
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
