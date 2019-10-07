# Frequently Asked Questions

### I'm new to RIDE and Earths Smart contracts, is there any tutorial or articles to start with?

Yes sure, you can check [_**Video Tutorials and Articles**_](/smart-contracts/video-tutorials-and-articles.md) section.

### Is smart contract functionality added in Earths ? If Yes, which languages are supported?

Yes, Earths has its own language for Smart Contracts. It is called [_**RIDE**_](/smart-contracts/ride-language/ride-language.md).

### Is it possible to convert an existing token to a smart token via a script, or must you implement a token swap?

Yes by using [_**smart assets**_](/smart-contracts/smart-assets.md) concept.

### I don't know about account scripts. Do you know where I could find appropriate documentation?

The best is to start with [_**as a developer guide.                        
**_](/getting-started/as-a-developer.md)

### How many Tx does earths have? will SC add another transaction type to the earthspay? Where can I find a valid SetScript transaction from testnet?

There are [_**14 tx types**_](/earths-api-and-sdk/earths-node-rest-api/example-transactions.md) on Earths and publishing a script for an account is one of those \(type 13 SetScript Tx\).

### Does Earths smart contracts have numbers similar Ethereum one's, 0x....?

No, but they are attached to accounts also, at least in the first version.

### When you develop a dapp on Earths, is it more appropriate to have a private earths blockchain or just your own full node on the regular mainnet ?

Neither of both, you don't have to have a node for deploying a SC. Nevertheless, for the dev i would recommend to use testnet.

### How can I create any interactive dApp?

[_**Smart contract**_](/smart-contracts/earths-contracts-language-description.md) on Earths can only answer 'yes' or 'no' for outgoing \(not incoming!\) transaction.

### How can I get string address from tx.sender in RIDE?

```js
let senderAddress = addressFromPublicKey(tx.senderPublicKey)
or 
let senderAddress= toBase58String(addressFromPublicKey(tx.senderPublicKey).bytes)
```

### What is a smart account?

The [_**smart account**_](/smart-contracts/smart-accounts.md) is an account with attached transactions checking **script**. In other words, a **script** which is attached to an account so the account can validate every transaction before confirming it.

### How to calculate fees for smart accounts and smart assets?

Please check the section [_**fee calculation for smart assets**_](/smart-contracts/smart-assets.md). For each time the script is called, total transaction’s fee increases by 0.004 Earths, you can find [_**full table**_](/earths-environment/earths-protocol/transactions-fees.md) here for all transactions.

### How can I get string address from tx.sender in RIDE?

```js
let senderAddress = addressFromPublicKey(tx.senderPublicKey)
or 
let senderAddress= toBase58String(addressFromPublicKey(tx.senderPublicKey).bytes)
```



