# Getting Started as a Developer

## Overview

This page introduces you to the things you'll need to get started on your journey.

This will give you all the information you need as a developer to get started in an easy to read and concise format.

## Client Libraries

Earths Client is supported by many libraries, please Get to know our client libraries\_** **\_and use them depending on which language you're familiar with:

* [_**Python: PyEarths**_](/earths-api-and-sdk/client-libraries/pyearths.md)
* [_**Java: EarthsJ**_](/earths-api-and-sdk/client-libraries/earthsj.md)
* [_**C\#: EarthsCS**_](/earths-api-and-sdk/client-libraries/earthscs.md)
* [_**TypeScript/JavaScript, Earths Signature Adapter**_](/earths-api-and-sdk/client-libraries/earths-signature-adapter.md) and [_**Earths Transactions**_](#)
* [_**C: EarthsC**_](/earths-api-and-sdk/client-libraries/earths-c.md)
* [_**Community Libraries**_](/earths-api-and-sdk/client-libraries/unofficial-libraries.md)

## Node REST API

[_**The Earths Node API**_](/earths-api-and-sdk/earths-node-rest-api.md) provides RESTful platform for implementing blockchain functionality in apps using Earths blockchain.

Use the API to integrate a variety of functionalities including orders, transaction history, and balances.

## Smart Contracts

Usually as a developer, you will need two things: **theoretical understanding** and **tools** to make your coding life easier, in our guide we will provide you with both:

### _**Theoretical Understanding **_

You will need to know:

* How Earths smart contract works \(You can go through our [_**smart contract guide**_](/smart-contracts/earths-contracts-language-description.md) to get more information about it\) and you can read about our [_**smart accounts**_](/smart-contracts/smart-accounts.md) and [_**smart assets.**_](/smart-contracts/smart-assets.md)

* Which programming language to use \(we're using our own language which called RIDE, [_**Get to know RIDE**_](/smart-contracts/ride-language/ride-language.md)_**\)**_.

let's suppose now that you understand the main idea of our smart contracts and you want to go through all functions and to understand how they work, please find here our [_**functions and standard library**_](/smart-contracts/ride-language/standard-library.md).

### _**Tools to help you with RIDE**_

In Earths, we always think about the best way to help external developers and because of that we will provide you with some useful tools:

* [_**Earths IDE **_](https://ide.earths.ga), Try out the new non-turing complete Earths smart contract language Ride by using our IDE.
* [_**Earths console and its commands**_](/smart-contracts/ride-language/earths-console-commands/earths-console-commands.md), Earths IDE has a Earths console feature which supports different commands.
* [_**Get to our Tutorials**_](/smart-contracts/video-tutorials-and-articles.md), We believe that the best way to learn is by practical examples.

## DEX API

The reason behind decentralized exchange is to perform secure exchange of assets issued on Earths platform.

The real-time trading is achieved thanks to the only centralized design element of our DEX - the order book Matcher, which matches incoming orders and execute trades at high speed, typically within milliseconds. There is no need to wait for the next block to know whether a trade has been executed successfully, this provides speed at the level of centralized exchange and the security of the decentralized protocol.

Please take a look to [_**Earths DEX API **_](/earths-api-and-sdk/dex-api/matcher.md)for more details and get the theoretical details by reading our [_**DEX article**_](/earths-environment/decentralized-cryptocurrency-exchange-dex.md)_**.**_

## Keeper API

Check the new [_**Earths Keeper**_](/earths-api-and-sdk/earths-keeper-api.md)\_** **\_browser extension which turns your browser into a keychain that enables you to sign transactions securely on third-party web resources without entering your seed or password. So now, if a Earths-integrated website or Dapp requires you to sign a transaction, you can do it with just a couple of clicks, right in your browser.

The extension will be particularly _**useful to developers**_ who want to embed Earths functionality in their projects, because it supports the Auth and Payment APIs. For testing purposes you can switch between using it on MainNet and TestNet.

