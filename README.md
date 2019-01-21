# Proof of Existence Ethereum Project
This project allows you to store any document (basically string) on blockchain and verify existence of any document. You can follow the directions to deploy simple proof of existence smart contract to ethereum rinkeby testnet and interact with it using terminal (truffle console).

## Pre-requisites

1) Metamask Chrome Extension
* Install the extension
* Accept the terms of use
* Enter a password for your account
* Save the 12 words shown in a file called '.secret' in the project directory

2) Infura account from [Infura website](https://infura.io)
* Create a project called 'proof-of-existence'
* Copy Project ID

3) Truffle
`$ sudo npm install -g truffle`
## How to install

3) Clone the project  and install the dependencies
* `$ git clone 'http://github.com/wakqasahmed/proof-of-existence'`
* `$ cd proof-of-existence`
* `$ npm install`

4) Configure wallet and deployment account
* Open the file `truffle-config.js` and replace the key in the following line with your infura Project ID (setup in Point#2)
`const infuraKey = "fj4jll3k.....";`

5) Deploy and interact with the contract on Ethereum Rinkeby Testnet
In your terminal
* Run the following command
`$ truffle migrate --network rinkeby`
* Enter the console
`$ truffle console --network rinkeby`

* Type the following command to get the instance:
`truffle(rinkeby)> var poe = await ProofOfExistence3.at(ProofOfExistence3.address)`
* Check any document's existence e.g.
`truffle(rinkeby)> poe.checkDocument("Hello Rinkeby!")`
Result: *false*
* Now, add a document to the blockchain, e.g.
`truffle(rinkeby)> poe.notarize("Hello Rinkeby!")`
* Recheck the document's existence e.g.
`truffle(rinkeby)> poe.checkDocument("Hello Rinkeby!")`
Result: *true*

##Wohoo! You have successfully deployed and executed solidity smart contract on ethereum rinkeby testnet. Have some rest and let it sink in :)