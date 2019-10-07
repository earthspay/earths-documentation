### POST /peers/connect
![master](https://img.shields.io/badge/MAINNET-available-4bc51d.svg)



Connect to peer.

**Request:**

```js
{
	"host":"127.0.0.1",
	"port":"9084"
}
```

### GET /peers/connected
![master](https://img.shields.io/badge/MAINNET-available-4bc51d.svg)



Returns list of all currently connected peers to the node.

**Response JSON example:**

```js
{
  "peers": [
    {
      "address": "18.231.27.49/18.231.27.49:7773",
      "declaredAddress": "N/A",
      "peerName": "zx 182",
      "peerNonce": 183759
    },
    {
      "address": "ec2-52-210-14-4.eu-central-1.compute.amazonaws.com/52.210.14.4:7773",
      "declaredAddress": "N/A",
      "peerName": "zx 217",
      "peerNonce": 1021800
    }
  ]
}
```

### GET /peers/blacklisted
![master](https://img.shields.io/badge/MAINNET-available-4bc51d.svg)



Returns list of all currently blacklisted peers to the node.

### GET /peers/all
![master](https://img.shields.io/badge/MAINNET-available-4bc51d.svg)



Returns list of all ever known not blacklisted peers with publicly available declared address.

