# Earths Platform Components

# Earths Client

[The Earths Client](https://client.earths.ga) can be [easily installed](/earths-client/install-earths-client.md) and used to perform most actions in the Earths Platform where users can issue, transfer and trade assets.

# Earths Wallet

* It’s a fully-featured client that lets you access all features of the Earths platform.

* It offers fiat integration, fast speeds, an intuitive interface, and custom tokens. It’s also constantly being updated.

* It allows to store, track, transfer and manage your cryptocurrencies, the Tokens that you issue or the Tokens that you acquire.

* The wallet has a built-in decentralized exchange platform that can be used to exchange assets, cryptocurrencies and fiat tokens.

# Decentralized cryptocurrency exchange \(DEX\)

[_**DEX**_](/earths-environment/earths-protocol/decentralized-cryptocurrency-exchange-dex.md) allows to place and execute orders for buying or selling cryptocurrency or Tokens for another cryptocurrency or exchanging them to other Tokens.

# Mobile apps

* Earths App is a mobile client for Earths Platform available for [iOS](https://itunes.apple.com/us/app/earths-wallet/id1233158971?mt=8) and [Android](https://play.google.com/store/apps/details?id=com.earthspay.wallet).
* The wallet is connected to public Earths nodes in order to retrieve your transactions and send payments.
* Get started with Earths App for [iOS](/earths-client/mobile-apps/iOS.md) and [Android](/earths-client/mobile-apps/android.md) devices.

# Earths Gateways

Fiat Gateways such as USD/EUR will allow you to exchange any token issued on the Earths platform \(or any other cryptocurrency like BTC/ETH/LTC/ZCash/BCH/Dash\) for “real” money, which can be deposited in a bank. All transactions between cryptocurrency to fiat or fiat to cryptocurrency will be recorded on the Earths blockchain. This is like mixing the best of both worlds \(i.e. centralized systems and decentralized systems\).

## Fiat Gateways

The Earths US dollar and EUR gateways are available within the Earths Client — allowing anyone to deposit and withdraw USD, EUR and use the backed token within the Earths ecosystem. Earths users can deposit USD and EUR via the secure gateways, receiving in return a token that is 100% backed by USD or EUR reserves. This can be held, transferred and exchanged for other tokens quickly and at low cost, and withdrawn back through the gateway into the traditional financial system when required.

the USD and EUR gateways offer Earths users an easy way to move money into the blockchain ecosystem, enabling them to invest in tokens and ICOs with fiat. This was always one of the key propositions for the Earths platform: the ability to send and trade with fiat-backed tokens.

**Note.** KYC/AML verification is needed to deposit and withdraw fiat money. However, KYC is not necessary for cryptocurrency transactions.

## Crypto Gateways

All currencies listed below are integrated in Earths through gateways. You can see gateways as a means to transfer a currency to and from the platform.

Current List of crypto gateways:

* [Transfers and Gateways](/earths-client/wallet-management.md)
* [iOS: Transfers and gateways](/earths-client/mobile-apps/iOS/wallet-management.md)
* [Android: Transfers and gateways](/earths-client/mobile-apps/android/wallet-management.md)

Cryptocurrency gateways can be used to move external currencies into and out of the Earths blockchain. Once the currencies have been confirmed as received by the gateway, the user’s wallet is credited with a Earths token that is 1:1 backed by the cryptocurrency held within the server. See more [What is a payment gateway](/earths-client/frequently-asked-questions-faq/transfers-and-gateways/payment-gateway.md)

Fees are minimal and the only delays are those required by blockchain confirmation times. We are planning to integrate more payment gateways in the future.

![](/_assets/Earths Gateways.png)Figure 1, Earths Crypto Gateways \(current and upcoming\).

# Nodes

Nodes are a critical part of our ecosystem. [Run a Earths node](/earths-full-node/how-to-install-a-node/how-to-install-a-node.md), help process transactions, ask the community to [lease their EARTHS](/earths-client/account-management/earths-leasing.md) to you and get paid for securing the network.

**Features:**

* A hosted server is adequate to run a node and no mining rigs or specialist hardware are required.
* It allows to mine EARTHS and MRTs \(Miners Reward Tokens\) and to act as a leasing pool to aggregate mining power from other users.
* Receiving rewards from the network by leasing your balance to a full node.

**Note.** The current number of nodes is 168 in 23 different countries.

# Mining nodes \(pools\)

* You don’t need any fancy hardware, just a simple hosted server and at least 1,000 EARTHS.
* You can run a public mining pool and have users lease their funds to you, thereby increasing your profits and sharing them with the community.

You can find the full list of Earths nodes for leasing with their corresponding address [_**HERE.**_](https://forum.earths.ga/c/pools)

# Official nodes with open API

1. [**EarthsGo**](http://www.earthsgo.com) is the foremost Earths node, with the biggest balance \(16,214,530 EARTHS\) and a thriving community of supporters. The node distributes the EarthsGo token to anyone who leases their funds to it.
2. [**Earthsnode.NET**](https://earthsnode.net)** **represents a developing community in Netherlands with a balance of 10,589,578 EARTHS. The node accepts multiple tokens for fees and has a growing list of supporters — as well as offering unique Earths merchandise.

**Note.** You can find a full nodes list at [dev.pyearths.org](http://dev.pyearths.org/generators/) and [Here](https://earths.ga/leasing#nodes) you can find a list of the top nodes by EARTHS balance.

# Matcher nodes

Matcher nodes are responsible for pairing orders and executing trades quickly, whilst they are still settled on the blockchain. You’ll need to send your orders to a Matcher. Orders are transferred to the matcher across an encrypted channel and will not be visible to others until it is executed. This largely eliminates the possibility of market manipulation. These nodes connect the seller to the buyer for a commission, and then fix the transaction in the Earths blockchain.

In principle, **any full node** can become a **Matcher**. Earths client connects to Matchers at [nodes.earths.ga](https://nodes.earths.ga/) by default.

Matchers will receive fees for the service they provide, adding an additional revenue stream for Earths full nodes.

**Note.** Earths node contains DEX Matcher which can be enabled while settings [_**the Earths node configuration file**_ ](/earths-full-node/configuration-parameters.md)in the section of Matcher Settings.

# MainNet / TestNet

1. **MainNet** - this is the real deal, the live Earths blockchain where you in the worst case could lose money if you are not careful. You can access the mainnet via a full node. it's integrated with the GUI in the Earths client, allowing anyone to use it without any technical knowledge or blockchain downloads.
2. **TestNet **- this is the test version of the Earths blockchain. [here](https://github.com/earthspay/Earths/releases) you'll find always the latest versions and newest features before they go live.
