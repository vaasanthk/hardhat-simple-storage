# Hardhat Simple Storage

![alt text](https://user-images.githubusercontent.com/176499/96893278-ebc67580-1460-11eb-9530-d5df3a3d65d0.png)

## About The Project

A demonstration of working with hardhat framework, deploying contracts and testing smart contracts with mocha and chai.

# Getting Started

## Requirements

- [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
  - You'll know you did it right if you can run `git --version` and you see a response like `git version x.x.x`
- [Nodejs](https://nodejs.org/en/)
  - You'll know you've installed nodejs right if you can run:
    - `node --version` and get an ouput like: `vx.x.x`
- [Yarn](https://classic.yarnpkg.com/lang/en/docs/install/) instead of `npm`
  - You'll know you've installed yarn right if you can run:
    - `yarn --version` and get an output like: `x.x.x`
    - You might need to install it with npm
- [Hardhat](https://hardhat.org/tutorial/setting-up-the-environment/)
  - Visit the site to learn more about hardhat framework.

# Built With

- [Node.js](https://nodejs.org/en/)
- [Solidity](https://docs.soliditylang.org/en/v0.8.15/)

## Setup

Clone this repo

```
git clone https://github.com/vaasanthk/hardhat-simple-storage
cd hardhat-simple-storage
```

Then install dependencies

```
yarn or npm i
```

## Usage

Compile your code

Run

```
yarn hardhat compile or npx hardhat compile
```

Deploy:

```
 yarn hardhat run scripts/deploy.js or npx hardhat run scripts/deploy.js
```

Testing:

```
yarn hardhat test or npx hardhat test
```

Test Coverage

```
yarn hardhat coverage or npx hardhat coverage

```

And you'll see and output file called `gas-report.txt`

## Local Deployment

If you'd like to run your own local hardhat network, you can run:

```
yarn hardhat node or npx hardhat node
```

And then **in a different terminal**

```
yarn hardhat run scripts/deploy.js --network localhost or npx hardhat run scripts/deploy.js --network localhost
```

And you should see transactions happen in your terminal that is running `npx hardhat node`

### Important localhost note

If you use metamask with a local network, everytime you shut down your node, you'll need to reset your account. Settings -> Advanced -> Reset account. Don't do this with a metamask you have real funds in. And maybe don't do this if you're a little confused by this.

## Deployment to a testnet or mainnet

1. Setup environment variables

You'll want to set your `RINKEBY_RPC_URL` and `PRIVATE_KEY` as environment variables. You can add them to a `.env` file, similar to what you see in `.env.example`.

- `PRIVATE_KEY`: The private key of your account (like from [metamask](https://metamask.io/)). **NOTE:** FOR DEVELOPMENT, PLEASE USE A KEY THAT DOESN'T HAVE ANY REAL FUNDS ASSOCIATED WITH IT.
  - You can [learn how to export it here](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key).
- `RINKEBY_RPC_URL`: This is url of the rinkeby testnet node you're working with. You can get setup with one for free from [Alchemy](https://alchemy.com/?a=673c802981)

2. Get testnet ETH

Head over to [faucets.chain.link](https://faucets.chain.link/) and get some tesnet ETH. You should see the ETH show up in your metamask.

3. Deploy

```
yarn hardhat run scripts/deploy.js --network rinkeby or npx hardhat run scripts/deploy.js --network rinkeby
```

### Verify on etherscan

If you deploy to a testnet or mainnet, you can verify it if you get an [API Key](https://etherscan.io/myapikey) from Etherscan and set it as an environment variable named `ETHERSCAN_API_KEY`. You can pop it into your `.env` file as seen in the `.env.example`.

In it's current state, if you have your api key set, it will auto verify rinkeby contracts!

However, you can manual verify with:

```
yarn hardhat verify ----constructor-args arguments.js DEPLOYED_CONTRACT_ADDRESS or npx hardhat verify --constructor-args arguments.js DEPLOYED_CONTRACT_ADDRESS
```

# Thank you!
