# Software Setup
In this section, we will explain what you need to setup your applicaiton

## Blockchain Network
Setting up blockchain networks means you are adding a network RPC configuration which is going to be available for users to select from.
>**Note**: this software currently supports EVM based blockchain and to intereact with Bitcoin you will have to get a [blockchain API Key](https://blockchain.com/explorer/api)

We have created a database seeder for some network that you can just seed into your database to safe you some time. To seed this networks, run the following command:

     php artisan db:seed --class=NetworkSeeder

>**Note**: if you set your APP_ENV enviroment variable to local or development it will seed a testnet blockchain networks into your database, however, setting it to production will seed mainnet blockchain networks into your database. Except for Bitcoin which will always seed mainnet.

You can also add blockchain manually:

1. Login and navigate to the admin panel
2. On the sidebar, click blockchain > networks
3. There you can perform CRUD operation on the blockchain network.

> **Note**: Admin user only have access to this module


## Staking Pool contract deployment
For users to be able to launch a staking pool for their token, you will need to deploy the staking pool smart contract to the blockchain network you have added.

To deploy the smart contract:

1. Login and navigate to the admin panel
2. On the sidebar, click blockchain > smart contracts
3. In the contract page click Add contract button
4. In the open  modal connect to your web3 wallet, select the network you are deploying to, select contract type
5. And click the Deploy button
