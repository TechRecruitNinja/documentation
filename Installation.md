
# Installation

Before you get started, ensure that you have the following installed on your machine:

1. Install Node.js - [https://nodejs.org/en/](https://nodejs.org/en/)
2. Install Node Version Manager – Switch between node versions
    + Mac/Linux - [https://github.com/creationix/nvm](https://github.com/creationix/nvm)
    + Windows - [https://github.com/coreybutler/nvm-windows](https://github.com/coreybutler/nvm-windows)
3. Install Automatic Version Switching for Node.js - [https://github.com/wbyoung/avn](https://github.com/wbyoung/avn) **_*Optional, if you prefer switching node versions manually instead_**
4. Install any IDE/Text Editor of your choice
    + Visual Studio Code - [https://code.visualstudio.com/](https://code.visualstudio.com/) 
    + Atom - [https://atom.io/](https://atom.io/)
    + Sublime Text 3 - [https://www.sublimetext.com/3](https://www.sublimetext.com/3)
5. Install any API Environment software of your choice
    + Postman - [https://www.getpostman.com/](https://www.getpostman.com/)
    + Insomnia - [https://insomnia.rest/](https://insomnia.rest/)


# Start the Installation
1. Navigate to `etc/hosts` file and Add `dev.recruit.com` right beside the line that displays `127.0.0.1` – This is to indicate that we are whitelisting dev.recruit.com as a localhost address. Sample of the edit below:
![whitelist](https://imgur.com/P1vGA33.png)


## Database

**Note:** **Requires MySQL version 5.7** to run the entire software application. For those requiring help downgrading from MariaDB to MySQL, kindly follow this tutorial - [https://gist.github.com/odan/c799417460470c3776ffa8adce57eece](https://gist.github.com/odan/c799417460470c3776ffa8adce57eece)

1.	Use any SQL IDE of your preference.
2.	Copy the Databse.sql script and run it in the IDE.
3.	Remember to change the user credentials.
4.	The database should be setup and ready to use.


## Portal

1.	Install and run Node v6.10.3
2.	`cd` into the TRN-Portal folder
3.	Run `npm i`
4.	Run `npm run start` to start the client-portal
5.	Navigate to [http://dev.recruit.com:8080](http://dev.recruit.com:8080) to view the portal and login
6.	Login credentials: `sampleuser@abc.com` / `user123`


## Server

1.	Install and run Node v8.1.2
2.	`cd` into the TRN-Server folder
3.	Run `npm i`
4.	Change the Database password inside `config/development.json` and `config/production.json`, under `sql` object - Required to be in sync with the password you chose for when setting up the database
5.	Run `npm run start` to start the back-end server
6.	Server is available for API CRUD operations via [http://dev.recruit.com:8030](http://dev.recruit.com:8030)


# Production Usage

In order to use the client portal and server in your production environment, kindly update the following files:

## Portal

1. Update the  `config/index.js` file.
2. Under the `build` object, update the `serviceUrl` with your Production URL of your choice.

### Building process
To compile the application, simply run `npm run build`. It will produce a `dist` folder in which will run in your production environment.

## Server

1. Update the `config/production.json` file.
2. Replace `<<YOUR_PRODUCTION_IP_ADDRESS>>` with your Production IP Address of your VPS instance.
2. Replace `http://<<YOUR_PORTAL_URL>>` and `https://<<YOUR_PORTAL_URL_WITH_HTTPS>>` with your Production Portal URL you have setup.

### Building process
To compile the application and run, simply run `npm run start-production`. This will initiate the Node.js application.

#### Tip
To run the server in the background, I would recommend installing and using PM2, an advanced [Node.js process manager](http://pm2.keymetrics.io/). It has all kinds of cool features such as logging, watch and reload, monitoring, startup scripts and many more.

**Installation** -  `npm install pm2 -g`
