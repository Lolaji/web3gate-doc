# Installation

To install the Web3Gate application you will need install the following software on your system

1. [Composer](https://getcomposer.org/)

## Downloaded File layout

This is the layout of your downloaded zip file after decompressed it.

    web3gate/
        source-code/     # contain the source code
        Documentation/   # documentation folder


## Installing Packages & Setup

### Software Requirements

     - PHP 8.0.1 or later
     - OpenSSL PHP Extension
     - PDO PHP Extension
     - Mbstring PHP Extension
     - Tokenizer PHP Extension
     - XML PHP Extension
     - Ctype PHP Extension
     - JSON PHP Extension
     - BCMath PHP Extension
     - FileInfo PHP Extension


### Install packages

Open the source-code folder with your terminal and run the following command to installed all the packages needed by this application. Make sure you are in the root directory of the source-code folder.

>**Note:** you will need to install composer to follow this step.

     $ composer install

### Create environment file

Now that you have install all the packages needed, create a .env file at the root of the application and copy the content of the .env.example into .env you have just create. You can use the following command to acheive this:

     $ cp .env.example .env

### Generate app key

Run the following command to generate app key:

     $ php artisan key:generate

### Configure the environment variable

After the .env file has been created, open the .env file and change the value of the following variables

     APP_NAME=you-app-name-here
     APP_ENV=local                           # development or production
     APP_DEBUG=false                         # true if you want to a display error message
     APP_URL=https://example.com             # the domain of the server you upload this to (http://localhost if running on your computer)

     DB_CONNECTION=mysql                     # pgsql for postgreSQL database
     DB_HOST=127.0.0.1
     DB_PORT=3306                            # 5432 for postgreSQL
     DB_DATABASE=database-you-created
     DB_USERNAME=database-username
     DB_PASSWORD=database-password

To be able to use bitcoin network in your application, you will need to get an API key from [blockchain.com](https://blockchain.com/explorer/api) and set it in your .env file

     BLOCKCHAIN_API_KEY=your-blockchain-api-key-here

### Database 

#### Migration
After setting up the .env file, now run the following command to setup the database.

     $ php artisan migrate

#### Seeding
Make sure to set the enviroment variable for the super admin as this will be the top level admin that has all the previledges, and you will use it for login.

     ADMIN_USERNAME=your-username
     ADMIN_EMAIL=your-email
     ADMIN_PASSWORD=your-password

then run:

     $ php artisan db:seed


### Run the app

You can now run the app by running the following command:

     $ php artisan serve

## Frontend Setup

Web3Gate uses [Vue.js](https://vuejs.org/) for it frontend and if you would like to make changes to your frontend, you must have [node.js](https://nodejs.org/) or [yarn](https://yarnpkg.com/) installed on your computer.

### Installing the node packages

Now you can install the node packages using the following command:

     $ npm install 
     // or
     $ yarn install

### Compile your project

To compile your project use the following command:

     $ npm run dev
     // or
     $ yarn dev