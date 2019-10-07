#Smart Contracts Tutorials

## 1. Multi Signature Using Earths IDE & EarthsJ

[_**In this tutorial**_](https://www.youtube.com/watch?v=o2msjSo0y0o&t=35s), the use case supposes that there are 3 people in a team and they hold common funds for corporate purposes. It is convenient for the team to make a decision about the allocation of common funds according to the majority decision, and they use a multi-signature account to do this \(smart account\). They create an account and do [`SetScriptTransaction`](https://ebceu4.github.io/earths-transactions/interfaces/setscripttransaction.html) with the **multisig account**. The idea here of a smart account is the following: before the transaction is submitted for inclusion in the next block, the account checks if the transaction meets certain requirements, defined in a script. The script is attached to the account so the account can validate every transaction before confirming it.

* [_**Source Code**_](https://github.com/Nazeim/Earths-Smart-Contracts-Tutorials)
* [_**Video**_](https://www.youtube.com/watch?v=o2msjSo0y0o&t=35s)
* [_**Earths IDE**_](https://ide.earths.ga)

## 2. Escrow Using Earths IDE & EarthsJ

[_**In this tutorial**_](https://www.youtube.com/watch?v=31dwYcgb65M&t=383s), we consider the problem of buying physical goods with cryptocurrencies. Should the buyer trust the seller and pay before receiving the goods or should the seller trust the buyer and ship the goods before receiving payment? This issue can be solved by using a third party escrow service. A well-known improvement uses Earths multisig feature. In this scheme, the money is not sent directly to the escrow service’s address, but instead, it is sent to a 2-of-3 multisig address with one key controlled by each of the transacting parties and one controlled by the mediator. When there is no dispute, the two transacting parties can together create the transfer transaction. Only when there is a dispute will the mediator get involved, collaborating with either the buyer or seller \(as appropriate\) to redeem the funds.

* [_**Source Code**_](https://github.com/Nazeim/Earths-Smart-Contracts-Tutorials/blob/master/src/main/java/Escrow.java)
* [_**Video**_](https://www.youtube.com/watch?v=31dwYcgb65M&t=383s)
* [_**Earths IDE**_](https://ide.earths.ga)

## 3. Create MultiSig Account via Earths Client

[_**In this tutorial**_](https://www.youtube.com/watch?v=OIQoheOYJw8), we went through Earths Client advanced features which are:

1. Get the transaction as JSON.
2. Attach a script to your account.

As a first step in our example, we created a script for 2 of 2 MultiSig account, Attach the script to our account via Earths client and then made a transfer transaction with two signatures.

## 4. Create MultiSig Account via Earths IDE tools

[_**In this tutorial**_](https://www.youtube.com/watch?v=8DKRGnwsBjk), we went through Earths IDE Tools which are:

1. Multisignature account wizard.
2. Transfer Tx generator.

As a first step in our example, we created and deployed a script for 2 of 2 MultiSig account by using the Multisignature account wizard and then made a transfer transaction with two signatures\(proofs\) by using Transfer Tx generator.

## 5. Blockchains: Earths Smart Accounts and Assets

[_**In this tutorial**_](https://www.youtube.com/watch?v=FEq4kU9mAas), We went through an Introduction in Earths Blockchain from the technical side with detailed description how Earths Smart Contracts work. Earths has a lot of interesting features, but smart contracts are the most interesting right now because Earths approach to Smart Contracts is absolutely different comparing with Ethereum, EOS and many other blockchains.

# Smart Contract Articles

Please, read our Hitchhiker’s Guide to Earths Smart Contracts which we divided into the following:

## 1. The Hitchhiker’s Guide to Earths Smart Contracts. Part1

[_**In this article**_](https://blog.earths.ga/the-hitchhikers-guide-to-earths-smart-contracts-part-1-b80aa47a745a), We focused on the idea of Earths Smart Accounts and what makes it different than other existing solutions.
We began with a brief introduction about some definitions of smart contracts then we explained about the difference between Bitcoin script, Ethereum Smart Contract and Earths Smart Accounts.

## 2. The Hitchhiker’s Guide to Earths Smart Contracts. Part 2

[_**In this part**_](https://blog.earths.ga/the-hitchhikers-guide-to-earths-smart-contracts-part-2-44621fd5a007), We focused more on the smart contracts language and tools for developers. We provided some use-cases implementation using our solution and explain more about our RIDE language.

## 3. Stateful Smart Accounts. Part 1

[_**In this article**_](https://blog.earths.ga/stateful-smart-accounts-part-1-315731d8c06), We explore the combination of DataTransactions and Smart Accounts.

## 4. Stateful Smart Accounts. part 2

[_**In this article**_](https://blog.earths.ga/stateful-smart-accounts-part-2-implementing-erc-20-and-nft-erc-721-step-by-step-7bac364fdadb), We prototyped two formats: ERC-20 and ERC-721, also known as “Collectibles” or “Non-fungible tokens”.

## 5. Microsoft Azure Cloud Features Earths Smart Assets and Smart Accounts

[_**In this article**_](https://blog.earths.ga/microsoft-azure-cloud-features-earths-smart-assets-and-smart-accounts-1a71b3c23c2b), We introduced Earths smart accounts and smart assets to developers on [Azure Marketplace](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/blockchain?search=blockchain&page=1) in a special extension for [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=earthspay.earths-ride), which simplifies the process of creating and operating smart contracts.

Two new virtual machine templates in Azure can be used for setting up new options on a public or private blockchain.
