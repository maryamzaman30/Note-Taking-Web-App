# University-of-London-Agile-Project

#### Directory Structure ####

```
app/
├── node_modules (removed, can be added via installation)
├── public/
|   ├── assets
|   |    ├── calculator.jpeg
|   |    ├── calculator.jpg   
|   |    ├── calculator(1).jpg
|   |    ├── equations.jpg
|   |    ├── equations.png
|   |    ├── graphs.png
|   |    └── scien-calc.jpeg
│   ├── script.js
│   └── style.css
├── routes/
│   ├── notes.js
│   ├── users.js
│   └── wolfram.js
├── views/
│   ├── createNote.ejs
│   ├── editNote.ejs
│   ├── homepage.ejs
│   ├── index.ejs
│   ├── login.ejs
│   └── register.ejs
├── .env
├── database.db (removed, can be added via creating a new database)
├── db_schema.sql
├── index.js
├── package-lock.json
├── package.json
├── README.md (This file)
└── secretkey.js
```

#### Versions used in this template ####

* NodeJS Version: 22.1.0
* npm Version: 10.7.0
* Sqlite3 Version: 3.41.2
Further information can be found in the `package.json` and `package-lock.json` file.

I suggest using the same versions of Node.js and npm as mentioned above to prevent any compatibility issues. 
Or atleast, ensure you're running Node.js version 16.x and npm version 8.x or higher to avoid potential problems.

## Installation

To get started with the Mathote the note-taking app, select & open the folder named `app` and follow the steps below:

### 1. Install Dependencies

Run the following command to install all necessary dependencies:

```npm install```

### 2. Building the Database

To initialize & create the database, use one of the following commands based on your system:

- For macOS/Linux:

```npm run build-db```

- For Windows:

```npm run build-db-win```

You can also run: 
```npm run clean-db``` to delete the database on Mac or Linux before rebuilding it for a fresh start
```npm run clean-db-win``` to delete the database on Windows before rebuilding it for a fresh start

### 3. Starting the Application

Run ```npm run start``` to start serving the web app (Access via http://localhost:3000)

## Creating an Account

To able to save your notes, you'll need to create an account. There's some authentication process implemented, you can use dummy email and dummy password to set up an account.

## Dependencies

A breakdown of the npm dependencies we have used and their uses in code:

-Project
├── axios@1.7.4 ```HTTP client for making requests.```
├── bcryptjs@2.4.3 ```Hashes passwords securely.```
├── dotenv@16.4.5 ```Loads environment variables.```
├── ejs@3.1.10 ```Templating engine for HTML.```
├── express-session@1.18.0 ```Manages user sessions.```
├── express@4.19.2 ```Web framework for Node.js.```
└── sqlite3@5.1.7 ```SQLite database bindings for Node.js.```

## Additional Libraries

There are no other libraries used beyond what is mentioned in the `package.json` file.

## Setup For .env file

.env file is already created for you but you need to obrain some IDs and store it in .env

**Obtaining SESSION_SECRET**

If you has followed previous steps and has Node.js installed, you can run the following command in the terminal:

node -e "console.log(require('crypto').randomBytes(32).toString('hex'));"

This command generates a random 32-byte string and converts it to hexadecimal format. Store it in .env file.

OR

Use the code written in secretkey.js to generate

**Note on Security:**

Do Not Share Your SESSION_SECRET: never share your SESSION_SECRET with anyone. This secret is essential for signing session cookies and ensuring the integrity of your sessions.

Store It Securely: Use environment variables or a secure configuration file (like a .env file) to store your SESSION_SECRET. This helps keep it separate from your source code and protects it from unauthorized access.

Understand Its Importance: Your SESSION_SECRET is vital for preventing session hijacking and ensuring that your users' sessions are secure. Treat it with the same level of care as you would with any sensitive credentials.

Manage Responsibly: If you ever suspect that your SESSION_SECRET has been compromised, make sure to change it immediately.

**Obtaining WOLFRAM_APP_ID**

In order to get the App ID, steps from https://github.com/Genbox/WolframAlpha were taken:

1. Go to https://developer.wolframalpha.com/portal/signup.html and create an account if you don't already have one.

2. After signing in, you will be directed to https://developer.wolframalpha.com/access, after you are directed, click on the button that says "Get an App ID"

3. Then fill in the Name & Description Box and select the type of API, you should select 'Full Results API'. Then click submit

4. After submitting, you will receive the ID, copy and paste this ID in .env file

4. It might shows an error "Error solving equation: Error from Wolfram Alpha API" when you enter an equation to solve on first try, there is nothing wrong with the code so just try to run the code again. This error occur due to API Usage Limits or Service Availability

**Note on Security:**

Please remember that your Wolfram|Alpha App ID is sensitive information. Do not share or publish your App ID in public repositories, forums, or any other accessible location. Exposing your App ID can lead to unauthorized use of your account, potential data breaches, and unexpected charges. If you no longer need your Wolfram|Alpha App ID or no longer using this app, please remove it from environment (e.g .env) to prevent any misuse.

## Running the App

After the initial setup, you should be able to access the application without further need for compilation or additional installations. If you face any problems, make sure that the version requirements for Node.js and npm are met and that all commands are executed in the 'app' folder. 

You should be able to ONLY run ```npm install```, ```npm run build-db```, and ```npm run start``` 

## User Guide

- **Create Note page**: No login is required. Users can type their notes, use equation solver, scientific and graphic calculators.

- **Save, edit or delete notes**: Requires account creation. Users can save multiple notes, edit or delete them.

## Link to Video

https://youtu.be/jHC6iWBWWCI
