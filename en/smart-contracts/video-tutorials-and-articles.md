# 1. Video Tutorials

Here you can find some video tutorials about our smart contracts use-cases which were build using:

1. [Earths IDE](https://ide.earths.ga)
2. [EarthJ \(Earths Java Library\) ](../development-and-api/client-libraries/earthsj.md)

## 1.1 Using Smart Contracts with Earths Console

[In this tutorial](https://www.youtube.com/watch?v=sOZuE9Ebfko&t=619s), we explain how to create, compile, deploy, and use Smart Contracts with Earths Console. The main use case here is 2-of-3 MultiSig account. This tutorial includes two parts:

**First Part:** this part includes console overview and how to write, compile and deploy the smart contract.

**Second Part:** this part includes steps to create, sign and send the transfer transaction to the network

* [_**Demo**_](https://demo.earths.ga)
* [_**Video**_](https://www.youtube.com/watch?v=sOZuE9Ebfko&t=619s)
* [_**Earths IDE**_](https://ide.earths.ga)

## 1.2 Multi Signature Using Earths IDE & EarthsJ

[In this tutorial](https://www.youtube.com/watch?v=o2msjSo0y0o&t=35s), the use case supposes that there are 3 people in a team and they hold common funds for corporate purposes. It is convenient for the team to make a decision about the allocation of common funds according to the majority decision, and they use a multi-signature account to do this \(smart account\). They create an account and do [`SetScriptTransaction`](https://ebceu4.github.io/earths-transactions/interfaces/setscripttransaction.html) with the **multisig account**. The idea here of a smart account is the following: before the transaction is submitted for inclusion in the next block, the account checks if the transaction meets certain requirements, defined in a script. The script is attached to the account so the account can validate every transaction before confirming it.

* [_**Source Code**_](https://github.com/Nazeim/Earths-Smart-Contracts-Tutorials)
* [_**Video**_](https://www.youtube.com/watch?v=o2msjSo0y0o&t=35s)
* [_**Earths IDE**_](https://ide.earths.ga)

## 1.3 Escrow Using Earths IDE & EarthsJ

[In this tutorial](https://www.youtube.com/watch?v=31dwYcgb65M&t=383s), we consider the problem of buying physical goods with cryptocurrencies. Should the buyer trust the seller and pay before receiving the goods or should the seller trust the buyer and ship the goods before receiving payment? This issue can be solved by using a third party escrow service. A well-known improvement uses Earths multisig feature. In this scheme, the money is not sent directly to the escrow service’s address, but instead, it is sent to a 2-of-3 multisig address with one key controlled by each of the transacting parties and one controlled by the mediator. When there is no dispute, the two transacting parties can together create the transfer transaction. Only when there is a dispute will the mediator get involved, collaborating with either the buyer or seller \(as appropriate\) to redeem the funds.

* [_**Source Code**_](https://github.com/Nazeim/Earths-Smart-Contracts-Tutorials/blob/master/src/main/java/Escrow.java)
* [_**Video**_](https://www.youtube.com/watch?v=31dwYcgb65M&t=383s)
* [_**Earths IDE**_](https://ide.earths.ga)

## 1.4 Earths Console Commands

Earths IDE has a **Earths console** feature which supports different commands.  
[In this video](https://www.youtube.com/watch?v=gBgLjg6nrvA&amp=&feature=youtu.be) we went through most of these commands with simple examples.

* [_**Video**_](https://www.youtube.com/watch?v=gBgLjg6nrvA&amp=&feature=youtu.be)
* [_**Earths Console Commands Examples**_](../technical-details/earths-contracts-language-description/earths-console-commands.md)

## 1.5 Create MultiSig Account via Earths Client

[In this tutorial](https://www.youtube.com/watch?v=OIQoheOYJw8), we went through Earths Client advanced features which are:

1. Get the transaction as JSON.
2. Attach a script to your account.

As a first step in our example, we created a script for 2 of 2 MultiSig account, Attach the script to our account via Earths client and then made a transfer transaction with two signatures.

## 1.6 Create MultiSig Account via Earths IDE tools

[In this tutorial](https://www.youtube.com/watch?v=8DKRGnwsBjk), we went through Earths IDE Tools which are:

1. Multisignature account wizard.
2. Transfer Tx generator.

As a first step in our example, we created and deployed a script for 2 of 2 MultiSig account by using the Multisignature account wizard and then made a transfer transaction with two signatures\(proofs\) by using Transfer Tx generator.

# 2. Smart Contract Articles

Please, read our Hitchhiker’s Guide to Earths Smart Contracts which we divided into the following:

## 2.1 The Hitchhiker’s Guide to Earths Smart Contracts. Part1

[_**In this article**_](https://blog.earths.ga/the-hitchhikers-guide-to-earths-smart-contracts-part-1-b80aa47a745a), we focused on the idea of Earths Smart Accounts and what makes it different than other existing solutions.  
We began with a brief introduction about some definitions of smart contracts then we explained about the difference between Bitcoin script, Ethereum Smart Contract and Earths Smart Accounts.

## 2.2 The Hitchhiker’s Guide to Earths Smart Contracts. Part 2

[_**In this part**_](https://blog.earths.ga/the-hitchhikers-guide-to-earths-smart-contracts-part-2-44621fd5a007), we focused more on the smart contracts language and tools for developers. We provided some use-cases implementation using our solution and explain more about our RIDE language.

