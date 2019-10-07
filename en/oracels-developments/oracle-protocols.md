# Oracle Protocols

Earths platform allows users to issue their own oracle and act as a data carrier, a reliable connection between Web APIs and your DApp. Oracles allow you to write data in the blockchain according to certain rules.

Based on the tool provided, some users will be able to describe their protocols and create Oracles, while other users will be able to easily find already created oracles and build DApp using this protocols.

## Steps to Create an Oracle

1. [Create a Earths account](/earths-client/account-management.md) or use method GenerateAddress to get the address along with private and public keys\(one address can create one oracle\). The provider can also use an existing account and keys.
2. Install [Earths Keeper](/earths-client/account-management/earths-keeper.md) for easy authorization.
3. Open [Earths Oracles](https://oracles.explorer.earths.ga/) and choose Create an Oracle. It needs to be authorized by Earths Keeper.
4. Fill the data provider information, create specification and send initiating [data transaction](/earths-environment/earths-protocol/data-transaction.md).
5. Oracle card created! Now you have a public card of your oracle, which will tell other users what kind of data and in what form your oracle will transfer from offchain to the blockchain. Next, start sending transaction in any convenient format supported by [Earths protocol.](/earths-environment/earths-protocol.md)

## Oracles Components

### Oracle Table

Earths Oracles interface is a portal containing information about:

* Oracles that are sorted into protocols categories.
* A login, which is a user-friendly tool that allows to create initializing data transaction.
* Oracles that are already created.

The main page of [Earths Oracles](https://oracles.explorer.earths.ga/), is a catalog of Oracles categories and there is a switch between Testnet and Mainnet.

[Earths Oracles](https://oracles.explorer.earths.ga/) allow to select a category, find Oracle by typing the known Earths address or Oracle name in the searching bar and a status filtering. After specifying the required search parameters, a table appears with the listed Oracles satisfying the query. It is possible to choose the Oracle and see detailed information about it on the Oracle card. You can press Refresh and all filters will be reset

### Oracle Card

The oracle card shows the oracle information, which the developer has filled out while creating or updating the oracle.

Create date, It represents the date of first Initializing data transaction.

Update date, It represents the date when a developer made some changes in the oracle description and sent last Initializing data transaction. These changes should be reflected in the field **Summary of Changes **from previous version.

Specification and Example show which format and data structure is proposed by this Oracle.

On the oracle card, there is a button **Show in explorer**. By clicking it, the initializing data transaction at [Earths Explorer](https://explorer.earths.ga/) will open.

## Create an Oracle

Only an authorized user can Create an oracle\(login with Earths Keeper\).

* If you login with Earths address from Testnet, then your Oracle will be created in the Testnet.
* If you login with Earths address from Mainnet,then your Oracle will be created in the Mainnet.

Here you need to fill in the inputs:

| Input | Description |
| :--- | :--- |
| Oracle name | Your Oracle name. |
| Specification | Specification kit. You can add or remove an arbitrary number of parameters by specifying their type, required and description. It is in this format that Oracle will need transmit data from the data source to the consumer. Oracle dont have to modify their data in order to be compatible with consumers, which can directly data to smart contracts. In order to maintain overall reliability, the data must relies to protocol with some version. We recommend in each transaction after initialize to specify parameter "version", which will indicate the version of the format recordable data structure. |
| Status | Select current Oracle status: development, test, production or archive. |
| Category | Select a category of data for better indexing in Earths Oracles for other users. |
| Address | Lock input. Earths address which you logined with Earths Keeper. |
| Network | Lock input. Network Mainnet or Testnet which you logined with Earths Keeper. |
| Link | Link to the data providers website. |
| Update frequency | How often the provider updates the data in time or blocks. |
| About | Goals and ideas of the current protocol, description of data sources or algorithm on the basis of which data appears, list of use cases, list of references with descriptions. |
| Example | Example of Oracle transaction. For a better understanding of your Oracle by other users insert a sample transaction in JSON in accordance with the format specified in the specification. |

## Update your Oracle

You can update the general attributes of the Oracle, such as an about, a link, or, for example, change a status, and you can also change the attributes of the specification. At change of attributes of the specification it is necessary to change the version of the Oracle protocol. Do not forget to change the Example. Always record your changes in the Summary of Changes from Previous Version field.

## Initializing data transaction

Initializing [data transaction](/earths-environment/earths-protocol/data-transaction.md) is a specific format set by Earths Platform, which allows you to categorize and describe Oracle data.

It is an usual data transaction that contains a well-defined set of attributes.

The Earths Oracles tool helps in a user-friendly interface to create such Initializing data transactions.

For a [data transaction](/earths-environment/earths-protocol/data-transaction.md) to be considered to initialize the Oracle, it must have a special attribute wpo\_oracle in the data\[\] array:

```js
{
    "key": "wpo_oracle",
    "type": "string",
    "value": "oracle"
}
```

This is key allows to find exactly the initialization data transaction from all Earths blockchain transactions.

Also needs add service keys: wpo\_createdate,wpo\_createid, wpo\_updatedate and wpo\_testnet\(only in testnet\).

## Data Provider Initialization

Parameters for the provider description

To go starting to write data in Earths blockchain transaction as Oracle, initialize data provider as Oracle.

| Key | Input in Earths Oracles | Type | Required | Value |
| :--- | :--- | :--- | :--- | :--- |
| wpo\_oracle |  | string | yes | ==”oracle” a special attribute for which the crawler is search the initialization data transaction |
| wpo\_testnet |  | boolean | yes\(only in testnet\) | ==true  only in Testnet |
| wpo\_createdate |  | Integer | yes | ==0 when you create Oracle first time timestamp first created version of Oracle |
| wpo\_createid |  | String | yes | =="origin" when you create Oracle first time transaction ID of the first created version of Oracle |
| wpo\_address | Address | String | yes | Earths address |
| wpo\_name | Oracle name | String | yes | Oracle name |
| wpo\_link | Link | String | no | Link |
| wpo\_protocol | Category | Integer | yes | protocol code |
| wpo\_status | Status | Integer | yes | current status of the provider defined by an integer. “3”\(archive\), “2”\(development\), “1”\(production\), “0”\(test\) |
| wpo\_description | About | String | no | oracle description |
| wpo\_frequency | Update frequency | String | no | frequency |
| wpo\_revisions | Summary of Changes from Previous Version | String | no | summary of revisions made |
| wpo\_specifation | Specification | Binary | no | base64 string. |
| wpo\_example | Example | Binary | no | base64 string. |
| wpo\_updatedate |  | Integer | yes | ==0 when you create Oracle first time timestamp new version of Oracle |

### Specification

In the value of key “wpo\_specifation” needs to enter the parameters of oracle specifications converted in base64.

One parameter of specifications are a set of four attributes each:

| Attributes of Parameters | Description |
| :--- | :--- |
| Name | Parameter name |
| Type | 1-String, 2- Integer, 3- Boolean, 4- Binary |
| Required | 1- yes, 0- no |
| Description | Parameter description |

For example, oracle will transmit three parameters:version, weather, temperature. Parameters version and weather are required.

Then the JSON array describing specification will look like this:

```js
[{
        "name": "version",
        "type": 1,
        "required": 1,
        "description": "current version of protocol"
    }, {
        "name": "weather",
        "type": 1,
        "required": 1,
        "description": "weather data"
    }, {
        "name": "temperature",
        "type": 2,
        "required": 0,
        "description": "сelsius"
    }
]
```

Then convert its JSON in base64 and it is being value of key “wpo\_specifation”:

```js
{
    "key": "wpo_specifation",
    "type": "string",
    "value": "base64:Clt7CiJuYW1lIjogInZlcnNpb24iLAoidHlwZSI6IDEsCiJyZXF1aXJlZCI6IDEsCiJkZXNjcmlwdGlvbiI6ICJjdXJyZW50IHZlcnNpb24gb2YgcHJvdG9jb2wiCn0sIHsKIm5hbWUiOiAid2VhdGhlciIsCiJ0eXBlIjogMSwKInJlcXVpcmVkIjogMSwKImRlc2NyaXB0aW9uIjogIndlYXRoZXIgZGF0YSIKfSwgewoibmFtZSI6ICJ0ZW1wZXJhdHVyZSIsCiJ0eXBlIjogMiwKInJlcXVpcmVkIjogMCwKImRlc2NyaXB0aW9uIjogItGBZWxzaXVzIgp9Cl0="
}
```

### Example

In the value of key “wpo\_example” needs to enter the example of oracle transaction based on their specification and converted in_base64_. An example of Oracle transaction in JSON:

```js
{
    "version": "1.00.95-release",
    "weather": "sun",
    "temperature": 23
}
```

Then convert its JSON in base64 and it is being value of key “wpo\_example”:

```js
{
    "key": "wpo_example",
    "type": "string",
    "value": "base64:ewoidmVyc2lvbiI6ICIxLjAwLjk1LXJlbGVhc2UiLAoid2VhdGhlciI6ICJzdW4iLAoidGVtcGVyYXR1cmUiOiAyMwp9"
}
```

### Usage

An example data transaction to initialize a data provider:

```js
{
    "type": 12,
    "version": 1,
    "senderPublicKey": "442hJo5S9U2jsdTvJ4v5zacH324XMnq3qUWCPmbkBWbZ",
    "fee": 300000,
    "timestamp": 1547218635000,
    "data": [{
            "key": "wpo_oracle",
            "type": "string",
            "value": "oracle"
        }, {
            "key": "wpo_createdate",
            "type": "integer",
            "value": 1548865781425
        }, {
            "key": "wpo_createid",
            "type": "string",
            "value": "CoQ79XjwgBiYxpzTVM2RQV1cFWeujF3JdwtAzdL6jx2r"
        }, {
            "key": "wpo_address",
            "type": "string",
            "value": "3Mso8hGr8dv4DK4nEY8fJykGpQkxK7PaZvs"
        }, {
            "key": "wpo_name",
            "type": "string",
            "value": "Example Stocks Oracle"
        }, {
            "key": "wpo_link",
            "type": "string",
            "value": "example.com"
        }, {
            "key": "wpo_protocol",
            "type": "integer",
            "value": 301
        }, {
            "key": "wpo_status",
            "type": "integer",
            "value": 1
        }, {
            "key": "wpo_description",
            "type": "string",
            "value": "An example of a public oracle containing information on various financial instruments in accordance with the requirements of the WPO002 protocol standard, such as stocks, commodities, fiat and cryptocurrencies."
        }, {
            "key": "wpo_frequency",
            "type": "string",
            "value": "Information is updated every 60 minutes."
        }, {
            "key": "wpo_revisions",
            "type": "string",
            "value": "Summary of revisions made"
        }, {
            "key": "wpo_specifation",
            "type": "string",
            "value": "base64:Clt7CiJuYW1lIjogInZlcnNpb24iLAoidHlwZSI6IDEsCiJyZXF1aXJlZCI6IDEsCiJkZXNjcmlwdGlvbiI6ICJjdXJyZW50IHZlcnNpb24gb2YgcHJvdG9jb2wiCn0sIHsKIm5hbWUiOiAid2VhdGhlciIsCiJ0eXBlIjogMSwKInJlcXVpcmVkIjogMSwKImRlc2NyaXB0aW9uIjogIndlYXRoZXIgZGF0YSIKfSwgewoibmFtZSI6ICJ0ZW1wZXJhdHVyZSIsCiJ0eXBlIjogMiwKInJlcXVpcmVkIjogMCwKImRlc2NyaXB0aW9uIjogItGBZWxzaXVzIgp9Cl0="
        }, {
            "key": "wpo_example",
            "type": "string",
            "value": "base64:ewoidmVyc2lvbiI6ICIxLjAwLjk1LXJlbGVhc2UiLAoid2VhdGhlciI6ICJzdW4iLAoidGVtcGVyYXR1cmUiOiAyMwp9"
        }, {
            "key": "wpo_updatedate",
            "type": "integer",
            "value": 1548866781425
        }
    ]
}
```

## Protocol codes table

| Category code | Protocol Code Value | Description |
| :--- | :--- | :--- |
| 100 | 100 | Algorithms & calculations\(random value for example\) |
|  | 101 | Pseudo random algorithms |
| 200 | 200 | Offline data source\(IoT, sensors, other hardware\) |
|  | 201 | Smart trackers\(smartphone, watch, collar, bracelet, etc.\) |
|  | 202 | Transfer, logistics, connected car, smart car |
|  | 203 | Smart home |
| 300 | 300 | Online data source\(rates, market data, weather, etc.\) |
|  | 301 | Market data & exchange rates |
|  | 302 | Weather data & forecasts |
|  | 303 | Sport & bets |
|  | 304 | Other blockchains |
|  | 305 | Time, date, calendar |
| 400 | 400 | Data Mangement |
|  | 401 | Rights |
|  | 402 | Media & Content |
|  | 403 | Document flow, work\(plans, activity records, etc.\) |
| 500 | 500 | DApps |
|  | 501 | Identification |
|  | 502 | Games |



