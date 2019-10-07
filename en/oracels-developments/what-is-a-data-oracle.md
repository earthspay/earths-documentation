# What is a data oracle

An oracle, in the context of blockchains and smart contracts, is a tool that determines and validates real-world data and submits this data to a blockchain to be used by smart contracts. In other words, an oracle is a data feed\(given by third party service\) created for use in smart contracts on the blockchain.

## Why blockchain needs data oracles

**How can smart contracts execute based on real-world conditions, such as price changes, game outcomes, or physical properties if the Earths blockchain has no way of directly accessing these data points through popular 3rd-party APIs?**

Blockchains do not have a way to access data outside of the chain\(they cannot access data outside their network\). Oracles provide external data and trigger smart contract executions when predefined conditions meet. Such a condition could be any data like weather temperature, successful payment, price fluctuations, etc. So Oracles aim to allow blockchain contracts to interact with the outside world.

Blockchains need a special way to query data from the outside world & import it in a blockchain format. Oracles have the single purpose of filling this role as an interface between the blockchain world & the outside world. With oracles, blockchain developers will be able to import & act on real-time data. This is necessary, because the nodes in the blockchain network which execute the smart contract code cannot retrieve external information by themselves.

# Oracles Types

The oracle can either bring data inside the blockchain \(inbound\) or inform an entity outside of the blockchain about a specific event \(outbound\). Oracles directly interact with data feeds such as APIs, scrappers & web hooks to extract, verify, & push this data to smart contracts on a number of blockchains.

