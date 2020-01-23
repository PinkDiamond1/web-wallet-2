# react-starter-kit

This is an example client side wallet built in React.js which allows you to make interactions with the OMG network from the browser.

Before you get started, make sure you have a local instance of elixir-omg running or have access to an already deployed network. Feel free to build on top of the functionalities which you see here.

NOTE: 
- This example application is using [`omg-js v3.0.0-alpha.14`](https://github.com/omisego/omg-js)

## Initial Setup

Make sure you have access to a Watcher endpoint, and the address of the deployed Plasma Contract. The wallet also requires an in-browser web3 wallet like MetaMask to sign transactions.

The endpoints for production deployment can be found [here](https://github.com/omisego/dev-portal/blob/master/guides/network_endpoints.md)

1. Install dependencies by running `yarn install` from the root

2. Create a `.env` file in the root and add your configuration with endpoints for `WATCHER_URL`, and `PLASMA_FRAMEWORK`.
```env
REACT_APP_WATCHER_URL=<watcher_url>
REACT_APP_PLASMA_FRAMEWORK=<plasma_framework_address>
REACT_APP_BLOCKEXPLORER_URL=<block_explorer_url>
REACT_APP_ETHERSCAN_URL=<etherscan_url>
```

3. Start the app by running `yarn start` from the root

## Running the starter-kit

Open up your browser and navigate to `http://localhost:3000`, Make sure your Metamask is currently unlocked. You should be able to see your account balance on both Root chain and Child chain.

From here, you can perform 3 actions:

1. Deposit into the OMG Network: After 12 blocks confirmations, your Rootchain balance will be updated.

2. Transfer funds on the OMG Network: Fill in the values for the Transfer fields and click OK. Depending on network congestion, you may have to wait for a little while for the transaction to be included in a block.

3. Exit your funds back to Rootchain: Fill in an address that has funds in the OMG Network and click on OK, your exit period will start. Do note that the exit period will be varied depending on the deployed contract environment. After the certain amount of time has passed, you will be able to process the exit and receive your funds back.

4. If the challenge period has passed, your exit will exist in an exit queue of that token. You can call process exits on this queue to receive your funds back.
