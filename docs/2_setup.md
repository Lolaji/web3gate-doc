# Setup
In this section, we will explain what you need to setup your applicaiton

## Blockchain Network
Setting up blockchain networks means you are adding a network RPC configuration which is going to be available for users to select from.
>**Note**: this software currently supports EVM based blockchain and to intereact with Bitcoin you will have to get a [blockchain API Key](https://blockchain.com/explorer/api)

During the installation process, some blockchain networks are seeded to your database.

You can also more by following the steps below:

1. Login and navigate to the admin panel
2. On the sidebar, click `blockchain > networks` navigation link
3. There you can perform CRUD operation on the blockchain network.

> **Note**: Only, admin user have access to this module


## Staking Pool contract deployment
For users to be able to launch a staking pool for their token, first you will need to deploy the staking pool smart contract to the blockchain network you have added.

To deploy the smart contract:

1. Login and navigate to the admin panel
2. On the sidebar, click `blockchain > smart contracts` navigation link
3. In the contract page click `Deploy` button
4. In the open modal, connect to your web3 wallet by clicking the `connect wallet` button, select the network you are deploying to, select contract type
5. And click the `Deploy` button
