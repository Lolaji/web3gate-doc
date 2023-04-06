# Installation

## Download & Unzip the script

Download the script and unzip the downloaded zip file on your computer. This is the layout of your downloaded zip file after unzipping it.

    web3gate/
        source-code.zip     # contain the source code
        Documentation/   # documentation folder


## Setting up on CPanel

### Installation Requirements



First, make sure your server meet up with the following PHP extension.

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


### Copying the script to your server

After extracting the downloaded zip file, upload the source-code.zip folder into the public_html folder by following the steps below:

1. In your CPanel dashboard, click `file manager` link
2. In the list of folder in your file manager, double click on the `public_html` folder
3. In your `public_html` page on the top of the page, finde and click the `upload` link
4. In the upload page, click select file and select the `source-code.zip` file and upload, or drag and drop the `source-code.zip` file on the upload section. You should wait for it to complete the upload
5. After the file is successfully uploaded, go back to the public_html folder and extract the uploaded `source-code.zip` file into the public_html folder. Make sure the public_html folder is empty.


### Wizard Installation
Web3Gate application shiped with click to install functionality, which gives you an easy way to get the application setup on your server without hustle.

After you have successfully copied the script source code to your serve, then open your browser and point to your website url and follow the steps below to get the application installed on your server.

#### Stop 1: Installation starting point

After the page load, your will be redirected to installation page for the first time. So continue by clicking the `Check Requirements` button,  then you will be navigated to the `Server Requirements` page.

<img src="https://web3gate.herokuapp.com/images/steps/1.png" />

#### Step 2: Server Requirements

In this page, the system will check if your server meets with proper software requirements to setup this application. If it does, all the requirements will be checked in green color, then proceed by clicking `Check Permissions` button which navigate you to `permission` page.

<img src="https://web3gate.herokuapp.com/images/steps/2.png" />

#### Step 3: Permissions

The following folders in the script need `775` permision to make the application access the folder.

     - storage/framework/
     - storage/logs/
     - bootstrap/caches/

<img src="https://web3gate.herokuapp.com/images/steps/3.png" />

If you see red `x` icon it means permission have not been given to this folder(s), so you will have to give this folder permission. However, if all the folder have a `check` green icons, it means all the folders have permission and you can proceed by clicking `Configure Environments` button which navigates to `Environment Settings` page.


#### Step 4: Environment Settings

In this page, click the `Form Wizard Setup` button, and you will be navigated to the `Environment` tab form.

<img src="https://web3gate.herokuapp.com/images/steps/4.png" />

#### Step 5: Environment Tab

Here you will:

     - Set your application name.
     - Set Environment or ignore with default
     - Set Debug or ignore with default
     - Set Log level or ignore with default
     - Set URL (Your Application URL)

<img src="https://web3gate.herokuapp.com/images/steps/5.png" />


#### Step 6: Database Tab

Here you will set your database credentails. Before setting this, make sure you have created a database in your server, then set the following field in the form field with the database credential you have created:

     - Database connection 
     - Host 
     - Port 
     - Database Name 
     - Database Username 
     - Database Password

<img src="https://web3gate.herokuapp.com/images/steps/6.png" />


#### Step 7: Application Tab

In this tab, you will only setup your email credentials for the application to be able to send email verification. Click the `Mail` accordion to setup the follow:

     - Driver
     - Host
     - Port
     - Username
     - Password
     - Encryption
     - From Address

<img src="https://web3gate.herokuapp.com/images/steps/8.png" />


#### Step 8: Administration Tab

In this tab you will setup your `username`, `email` and `password` to login as the super admin of the system. Then, in the `Blockchain Network` field, you will choose either the `mainnet` or `testnet`. Choosing `mainnet` seed default mainnet blockchain network to you database while choosing `testnet` seed testnet blockchain network.

For the the Blockchain key, you will have to obtain blockchain key from [blockchain API](https://blockchain.com/explorer/api) for the bitcoin  functionality to work. If you don't provide this, the bitcoin network will not work.

Finally you will setup your `infura ID`. You will need to go to [infura.io](https://infura.io) to obtain an ID. Though, it is not mandatory.

<img src="https://web3gate.herokuapp.com/images/steps/9.png" />

After everything is setup, click `Install` button.

>**Note**: If when you click `Install` button you get a `Page not working` error, what you have to do is to just reload the page by clicking the reload button on the page or the refresh icon in your browser bar.

#### Step 9: Finalizing the intallation

After every thing is install successfully, you will see this page. Click the `Click here to exit` button and you will be redirected to the home page.

<img src="https://web3gate.herokuapp.com/images/steps/10.png" />

Now you can navigate to the login page and login with the credential you provided in the `Administration Tab` form. When login is successful you will be redirected to the user dashboard, and if you want to go to the admin panel, click your `username` at the top-right coner in the navigation and a dropdown opens, you will see `Admin Panel` link in the dropdown, click it and you will be navigated to the admin panel.

<img src="https://web3gate.herokuapp.com/images/home.png" />

### Manual Setup

#### Step 1: Configure the environment variable

After the successful upload, In the public_html, find and open the .env file and change the value of the following variables

     APP_NAME=you-app-name-here
     APP_ENV=local                           # development or production
     APP_DEBUG=false                         # true if you want to a display error message
     APP_URL=https://example.com             # the domain of the server you upload this to

     DB_CONNECTION=mysql
     DB_HOST=127.0.0.1
     DB_PORT=3306
     DB_DATABASE=database-you-created        # the database name you just created
     DB_USERNAME=database-username           # your database username
     DB_PASSWORD=database-password           # your database password

>**NOTE**: For the environment variable `APP_ENV`, if you set it to `local` or `development` the testnet blockchain network will be seeded into your database, except the bitcoin network that will seed mainnet. Setting it to `production` will seed mainnet blockchain network.

#### Step 2: Admin Login Setup 

Make sure to set the enviroment variable for the super admin as this will be the top level admin that has all the previledges, and you will use it for login.

     ADMIN_USERNAME=your-username
     ADMIN_EMAIL=your-email                  # use for login
     ADMIN_PASSWORD=your-password            # use for login


#### Step 3: Email Setup

Set the email environment variable for the application to be able to send email.

     MAIL_DRIVER=smtp                        # email server
     MAIL_HOST=smtp.mailtrap.io              # email host name
     MAIL_PORT=2525                          # email port
     MAIL_USERNAME=null                      # email address
     MAIL_PASSWORD=null                      # email password
     MAIL_ENCRYPTION=ssl                     # or tls
     MAIL_FROM_ADDRESS=                      # email address


#### Step 4 Blockchain API Setup

To be able to use bitcoin network in your application, you will need to get an API key from [blockchain.com](https://blockchain.com/explorer/api) and set it in your .env file

     BLOCKCHAIN_API_KEY=your-blockchain-api-key-here

then click `save and install`


### Step:5 Finalize Installation

After everything is setup, click 


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