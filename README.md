# Building a Decentralized Crowdfunding Platform on Celo Blockchain

## Table of Contents

- [Introduction](#introduction)
- [Pre-requisites](#pre-requisites)
- [Requirements](#requirements)
- [Overview of Celo Crowdfunding](#overview-of-celo-crowdfunding)
- [Understanding Celo’s Crowdfunding System](#understanding-celos-crowdfunding-system)
- [Why is Crowdfunding Important?](#why-is-crowdfunding-important)
- [Benefits and Challenges of Using Decentralized Crowdfunding](#benefits-and-challenges-of-using-decentralized-crowdfunding)
- [Fetching Real-Time Information](#fetching-real-time-information)
- [Ensuring Reliability with Crowdfunding](#ensuring-reliability-with-crowdfunding)
- [Setting Up Celo’s Crowdfunding Integration](#setting-up-celos-crowdfunding-integration)
  - [Install Celo’s Crowdfunding Library](#install-celos-crowdfunding-library)
  - [Import the Crowdfunding Contract](#import-the-crowdfunding-contract)
  - [Initialize the Crowdfunding Contract](#initialize-the-crowdfunding-contract)
  - [Retrieve Data from the Crowdfunding](#retrieve-data-from-the-crowdfunding)
- [Deploy and Test](#deploy-and-test)
- [Retrieving External Data in Smart Contracts](#retrieving-external-data-in-smart-contracts)
  - [Define the Data Request](#define-the-data-request)
  - [Query the Crowdfunding](#query-the-crowdfunding)
  - [Fulfill the Data Request](#fulfill-the-data-request)
  - [Test and Validate](#test-and-validate)
- [Ensuring Data Reliability and Security](#ensuring-data-reliability-and-security)
  - [Data Verification](#data-verification)
- [Conclusion](#conclusion)

## Introduction

Attention Newbie Developers: Supercharge Your DApps with Celo Blockchain Crowdfunding!

Are you ready to take your decentralized applications (DApps) to the next level? In this tutorial, we’re diving into the exciting world of Celo blockchain crowdfunding. They hold the key to seamlessly integrating external data into your Smart Contracts and DApps, making them more powerful and reliable than ever before.

Why is accessing off-chain data crucial? Well, imagine your dApp needing real-world information like market prices, weather updates, or even sports scores. With Celo’s decentralized crowdfunding, you can easily fetch and verify this external data within the secure Celo ecosystem. The possibilities are endless!

In this beginner-friendly tutorial, we’ll walk you through harnessing the incredible capabilities of Celo’s stable crowdfunding system. No need to worry about complex technicalities - we’ve got you covered with clear illustrations and step-by-step instructions.

By the end of this tutorial, you’ll empower your DApps to securely tap into real-world data, ensuring they’re as reliable as possible. It’s time to unlock a world of possibilities and create DApps that stand out from the crowd.

Don’t miss this opportunity to level up your development skills and make a real impact in the blockchain space. Join us on this thrilling journey as we unravel the potential of Celo blockchain crowdfunding!

Get ready to revolutionize your DApps - let’s dive in!

## Pre-requisites

Before we embark on this thrilling journey, let’s ensure you have the essentials in your developer toolkit:

- **Solidity Programming Language:** Familiarity with Solidity, the language of smart contracts will be your key to success throughout this tutorial. Don’t worry if you’re new to it - we’ll provide explanations and examples along the way. https://ethereum.org/en/developers/docs/smart-contracts/
- **Basics of the Celo Platform:** To make the most of this tutorial, it’s beneficial to have a foundational understanding of the Celo platform. But don’t fret if you’re not there yet - we’ll guide you through the fundamentals, ensuring you’re ready to soar! https://dacade.org/communities/celo, https://docs.celo.org/developer/walkthrough/hello-contract-remote-node
- **Blockchain Technology and Smart Contracts:** If you’ve got some knowledge of blockchain technology and smart contracts, you’re already ahead of the game. However, if you’re new to these concepts, fear not! We’ll provide you with the necessary explanations to grasp the magic behind decentralized applications. https://dacade.org/communities/blockchain
- **Read This Article for Basic Understanding on Celo Crowdfunding:** To set the stage for our adventure, we recommend taking a quick detour to read an article that offers a basic understanding of Celo Crowdfunding. Visit Celo Crowdfunding Basics and familiarize yourself with this crucial component of the Celo ecosystem. https://medium.com/@ajaotosinserah/smart-contract-development-on-celo-a-beginners-guide-to-writing-and-deploying-a-contract-on-the-f25a0941e527

With these essentials in your arsenal, you’re well-prepared to delve into the captivating world of Celo Crowdfunding. We’re here to guide you every step of the way, ensuring that you grasp the concepts and gain hands-on experience with ease.

Get ready to unlock the power of Celo Crowdfunding and witness firsthand how it can revolutionize your smart contracts. Let’s set off on this knowledge-packed adventure together!

## Requirements

Before we kickstart this exhilarating experience, let’s make sure you have the essentials in place:

- **A Working Development Environment:** You’ll need a modern text editor (like Visual Studio Code), a recent version of Node.js (including npm), and Git installed on your machine.
- **Celo Extension Wallet or a Similar Wallet Compatible with Celo:** You’ll need a Celo wallet to interact with the Celo blockchain. We recommend using the Celo Extension Wallet, which is a browser extension that allows you to manage your Celo accounts and sign transactions.
- **Familiarity with JavaScript and Solidity:** This tutorial assumes that you have a basic understanding of JavaScript and Solidity, the programming language used to write smart contracts on the Ethereum and Celo blockchains.
- **An Internet Connection:** You’ll need an internet connection to interact with the Celo blockchain and fetch data from the crowdfunding platform.

# Overview of Celo Crowdfunding

Crowdfunding is a method of raising capital through the collective effort of friends, family, customers, and individual investors. This approach taps into the collective efforts of a large pool of individuals—primarily online via social media and crowdfunding platforms—and leverages their networks for greater reach and exposure.

In the context of blockchain technology, crowdfunding takes on a new dimension. With Celo’s blockchain, we can create a decentralized crowdfunding platform. This means that the platform is not controlled by any single entity, and transactions are transparent and secure.

## Understanding Celo’s Crowdfunding System

Celo’s crowdfunding system is built on smart contracts. A smart contract is a self-executing contract with the terms of the agreement directly written into code. They allow trusted transactions and agreements to be carried out among disparate, anonymous parties without the need for a central authority, legal system, or external enforcement mechanism.

In our crowdfunding system, each project will be a new smart contract on the blockchain. This contract will hold the funds raised by the project and will have rules in place to determine how these funds can be withdrawn by the project creator.

## Why is Crowdfunding Important?

Crowdfunding is important because it provides opportunities for entrepreneurs, artists, and individuals to realize their goals and bring their projects to life. It democratizes access to capital and allows anyone, anywhere, to support projects they believe in.

In the context of blockchain, crowdfunding also demonstrates the power of decentralized finance. It shows how blockchain can remove intermediaries, reduce costs, and increase transparency in financial transactions.

## Benefits and Challenges of Using Decentralized Crowdfunding

Decentralized crowdfunding offers several benefits over traditional crowdfunding:

- **Transparency:** All transactions are recorded on the blockchain, making it easy for backers to see exactly where their money is going.
- **Security:** Funds are stored in a smart contract on the blockchain, making it nearly impossible for funds to be misused or stolen.
- **Accessibility:** Anyone, anywhere in the world, can participate in a crowdfunding campaign on the blockchain.

However, there are also challenges to consider:

- **Smart contract bugs:** If there are bugs in the smart contract code, funds could be lost or stolen.
- **Regulatory uncertainty:** The legal status of decentralized crowdfunding is still unclear in many jurisdictions.

Despite these challenges, the potential benefits of decentralized crowdfunding make it an exciting area for exploration and innovation.

## Fetching Real-Time Information

In a crowdfunding platform, it’s important to have real-time information about each project. This includes information like the amount of funds raised, the number of backers, and the time remaining in the campaign.

With Celo’s blockchain, we can fetch this information directly from the smart contract. Each time a backer contributes funds to a project, the smart contract will automatically update its state. We can then fetch this state from the blockchain to get real-time information about the project.

## Ensuring Reliability with Crowdfunding

Reliability is crucial in a crowdfunding platform. Backers need to trust that the platform will handle their funds securely and that the information presented about each project is accurate.

With Celo’s blockchain, we can ensure reliability in several ways:

- **Secure smart contracts:** By writing secure smart contract code and thoroughly testing it, we can minimize the risk of bugs that could lead to lost or stolen funds.
- **Transparent transactions:** Because all transactions are recorded on the blockchain, backers can verify for themselves that their funds have been correctly allocated.
- **Immutable records:** Once a transaction has been recorded on the blockchain, it cannot be changed. This ensures that the history of each project is permanently recorded and cannot be tampered with.

## Setting Up Celo’s Crowdfunding Integration

Now that we understand the basics of Celo’s crowdfunding system, let’s start building our platform.

### Install Celo’s Crowdfunding Library

We will be building the crowdfunding platform on Celo using smart contracts written in Solidity. Solidity is a statically-typed programming language designed for developing smart contracts that run on the Ethereum Virtual Machine, also known as EVM. Smart contracts are self-executing contracts with the terms of the agreement directly written into code.

The tools we’ll be using include:

- Node.js: This is a JavaScript runtime built on Chrome’s V8 JavaScript engine. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices. We’ll be using Node.js to create our backend server.

- Truffle Suite: This is a development environment, testing framework, and asset pipeline for Ethereum (and by extension, Celo, which is compatible with Ethereum). We’ll use Truffle to compile and deploy our smart contracts.

- Celo’s ContractKit SDK: This is a software development kit provided by Celo to help developers build on their platform. We’ll use ContractKit to interact with the Celo network, including sending transactions, interacting with smart contracts, and more.

To install the required libraries, you can run the following command in your terminal:

```bash
npm install @celo/contractkit@1.0.1 express@4.17.1 web3@1.5.3
```

This command does the following:

- `npm` install is the command used to install Node.js packages.
- `@celo/contractkit@1.0.1` is the package for Celo’s ContractKit SDK. The @1.0.1 specifies the version of the package to install.
- `express@4.17.1` is the package for Express.js, a minimal and flexible Node.js web application framework.
- `web3@1.5.3` is the package for Web3.js, a collection of libraries that allow you to interact with a local or remote Ethereum node using HTTP, IPC, or WebSocket.
  
After running this command, these packages will be installed in your Node.js project, and you can require them in your JavaScript files as needed. They provide the functionality necessary for interfacing with the Celo network, creating a backend server, and communicating with the Celo nodes.

### Import the Crowdfunding Contract

In this step, we will create a placeholder for our crowdfunding smart contract. This contract will be written in Solidity, a statically-typed programming language designed for developing smart contracts that run on the Ethereum Virtual Machine, also known as EVM.

Here’s how to do it:

- Create a new file in your project directory and name it `Crowdfunding.sol`.

- Add the following code to the `Crowdfunding.sol` file:

```bash
pragma solidity ^0.5.16;

contract Crowdfunding {
    // ... contract code goes here ...
}
```

Let’s break down what this code does:

- `pragma solidity ^0.5.16;` : This line specifies the version of Solidity that the contract is written in. It’s important to specify the correct version to ensure that the contract compiles correctly.

- `contract Crowdfunding {...}` : This line declares a new contract named Crowdfunding. The body of the contract is enclosed in curly braces {...}. Right now, the body of the contract is empty because this is just a placeholder.

### Initialize the Crowdfunding Contract

In this step, we will initialize the crowdfunding contract. This is a crucial step as it sets up the connection to the Celo blockchain and allows us to interact with our smart contract.

Here’s the code you need to add to your `server.js` file:

```bash
const ContractKit = require('@celo/contractkit');
const Web3 = require('web3');

const web3 = new Web3('https://alfajores-forno.celo-testnet.org');
const kit = ContractKit.newKitFromWeb3(web3);

// ... rest of the code goes here ...
```

Let’s break down what this code does:

- `const ContractKit = require('@celo/contractkit');` : This line imports the ContractKit library from Celo. ContractKit is a powerful tool that simplifies interaction with the Celo blockchain.

- `const Web3 = require('web3');` : This line imports the Web3 library. Web3.js is a collection of libraries that allow you to interact with a local or remote Ethereum node using HTTP, IPC, or WebSocket.

- `const web3 = new Web3('https://alfajores-forno.celo-testnet.org');` : This line creates a new instance of Web3 and connects it to the Celo Alfajores testnet. Alfajores is one of Celo’s test networks (or testnets) that developers can use to test their applications.

- `const kit = ContractKit.newKitFromWeb3(web3);` : This line initializes a new instance of ContractKit using the Web3 instance. This kit will allow us to interact with our crowdfunding contract on the Celo blockchain.

The rest of the code will go after these lines. This setup is necessary for any application that interacts with the Celo blockchain. It establishes the connection to the blockchain and sets up the tools we need to interact with it.

### Retrieve Data from the Crowdfunding

In this step, we will add a function to retrieve data from the crowdfunding contract. This function will allow us to fetch information about a specific project.

Here’s the code you need to add to your `server.js` file:

```bash
app.get('/projects/:id', async (req, res) => {
    const crowdfunding = new kit.web3.eth.Contract(
        // ABI of the crowdfunding contract
        [],
        // Address of the crowdfunding contract
        '0x...'
    );

    const project = await crowdfunding.methods.getProject(req.params.id).call();

    res.send(project);
});
```

Let’s break down what this code does:

- `app.get('/projects/:id', async (req, res) => {...});` : This line creates a new route in our Express.js server. The route is /projects/:id, where :id is a placeholder for the ID of the project we want to fetch. The async keyword is used because we’ll be making asynchronous calls to the blockchain.

- `const crowdfunding = new kit.web3.eth.Contract([...], '0x...');` : This line creates a new instance of our crowdfunding contract. The new kit.web3.eth.Contract part is a function provided by Web3.js that creates a new contract instance. The first argument is the ABI of the contract, and the second argument is the address of the contract on the blockchain.

- `const project = await crowdfunding.methods.getProject(req.params.id).call();` : This line calls the getProject method of our contract. The `req.params.id` part is the ID of the project we want to fetch, which comes from the URL of the request. The await keyword is used because calling a contract method is an asynchronous operation that returns a promise.

- `res.send(project);` : This line sends the project data back to the client as the response to their request.

The `getProject` method is a placeholder for now - we’ll implement it in the next steps. This method will fetch data about a specific project from the blockchain and return it.

## Deploy and Test

After setting up the server and initializing the crowdfunding contract, the next step is to deploy and test the platform.

To deploy the server, you need to execute the following command in your terminal:

```bash
node server.js
```

Upon running this command, you should see a message indicating that the server is up and running. This confirms that your server has been successfully deployed.

Now, it’s time to test the platform. You can do this by opening your web browser and navigating to `http://localhost:3000/projects/1`. This URL corresponds to a route in your server that fetches data about the project with an ID of 1. If everything is set up correctly, you should be able to see the data for project 1 displayed in your browser.

This process of deploying and testing is crucial as it allows you to verify that your platform is functioning as expected. It provides an opportunity to catch and fix any issues or bugs before the platform is released to end-users.

## Retrieving External Data in Smart Contracts

In the context of a crowdfunding platform, external data can be crucial. For instance, you might want to fetch real-time exchange rates to allow contributions in different currencies, or you might want to integrate with a third-party service to perform KYC checks on project creators.

With Celo’s blockchain, you can fetch external data using oracles. An oracle is a way for a blockchain to interact with external data. You can think of it as a data feed that your smart contract can read from. In a full tutorial, we would dive deeper into how to set up and use an oracle with Celo.

## Define the Data Request

The first step in using an oracle is to define your data request. This is essentially specifying the data you want the oracle to fetch.

In your example, you’re requesting the current exchange rate from cGLD to USD. Here’s how you might define this request:

```javascript
const dataRequest = {
  currency: 'cGLD',
  to: 'USD',
};
```

In this code:

- `dataRequest` is the request you’re sending to the oracle.
- `currency` specifies the currency you’re converting from, which is ‘cGLD’ in this case.
- `to` specifies the currency you’re converting to, which is ‘USD’ in this case.

## Query the Oracle

After setting up the oracle, you need to query it with your data request. The oracle fetches the data from an external source and returns it to your smart contract. Here’s how you might do it:

```javascript
const exchangeRate = await oracle.getExchangeRate(dataRequest);
```

In this code:

- `oracle` is the oracle you’ve set up.
- `getExchangeRate` is a function that fetches the exchange rate.
- `dataRequest` is the request you’re sending to the oracle.
- `exchangeRate` is the data returned by the oracle.

## Fulfill the Data Request

Once the oracle has fetched the required data (in this case, the exchange rate), you can use it in your smart contract. Here’s how you might use it to calculate the amount of cGLD (a digital asset) a contributor will receive for their contribution in USD:

```javascript
const contributionInUSD = 100;
const contributionInCGLD = contributionInUSD * exchangeRate;
```

In this code:

- `contributionInUSD` is the amount of contribution in USD, which is 100 in this case.
- `exchangeRate` is the current exchange rate between USD and cGLD fetched by the oracle.
- `contributionInCGLD` is the calculated amount of cGLD that the contributor will receive. It’s calculated by multiplying the contributionInUSD by the exchangeRate.

This way, the oracle fetches the data (exchange rate), and the smart contract uses this data to perform its functions (calculating the amount of cGLD a contributor receives). This allows the smart contract to interact with real-world data and perform operations based on it.

## Test and Validate

After setting up the oracle integration, it’s important to test it thoroughly. Write tests that cover all possible scenarios and edge cases. Make sure the oracle correctly fetches data and your smart contract correctly uses this data.

## Ensuring Data Reliability and Security

When using an oracle, it’s crucial to ensure the data it provides is reliable and secure. Here are some strategies to achieve this:

- Use a Trusted Oracle: 
Ensure you’re using an oracle that is known to be reliable and secure. Celo provides its own oracle for fetching exchange rates, which is likely to be more reliable than a third-party oracle.

- Verify the Data: 
Before using the data provided by the oracle, verify it against other sources. This can help you catch any inaccuracies or manipulations.

- Handle Errors Gracefully: 
If the oracle fails to fetch the data or returns an error, make sure your smart contract handles this gracefully. This might mean reverting any transactions that rely on the oracle data.

## Data Verification

Data verification is a crucial aspect of working with oracles. Here are some strategies for verifying oracle data:

- Cross-reference with other sources: If possible, cross-reference the oracle data with other reliable sources. This can help you catch any discrepancies.
  
- Check the update time: Oracles should provide the time of the last update. Ensure this is recent enough for your needs.
  
- Use multiple oracles: For added reliability, you can use multiple oracles and take the median of their responses.

## Conclusion

Congratulations! You’ve just built a simple DApp on the Celo blockchain. This is just the beginning - there’s much more you can do with Celo and ContractKit. Happy coding!


