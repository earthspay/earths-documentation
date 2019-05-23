# Burn transaction

**Burn transaction** is a transaction that burns tokens.

## Data structure v2

| Field order number | Field name | Field type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Transaction multiple version mark | Byte | 1 | Indicates that this is a transaction with a [data structure](/blockchain/transaction-data-structure.md) of version 2 or above. <br>The value has to be equal to 0 |
| 2 | Transaction type | Byte | 1 | ID of the [transaction type](/blockchain/transaction-type.md). <br>The value has to be equal to 6 |
| 3 | Version | Byte | 1 | Version number of the data structure of the transaction.  <br>The value has to be equal to 2 |
| 4 | Chain ID | Byte | 1 | Determines the network where the transaction will be published to. <br>84 for [testnet](/blockchain/testnet.md), 87 for [mainnet](/blockchain/mainnet.md) |
| 5 | Sender's public key | Array of bytes | 32 | Account public key of the sender |
| 6 | Asset ID | Array of bytes | 32 | ID of the asset to burn |
| 7 | Quantity | Long | 8 | Amount of tokens to burn |
| 8 | Fee | Long | 8 | [Transaction fee](/blockchain/transaction-fee.md) in [WAVELETs](/blockchain/token/wavelet.md) |
| 9 | Timestamp | Long | 8 | Unix time of transaction publication to the network |
| 10 | Proofs | Array of [proofs](/blockchain/transaction-proof.md) | `S` | If the array is empty, then `S`= 3. <br>If the array is not empty, then `S` = 3 + 2 × `N`+ (`P1` + `P2` + ... + `Pn`), where `N` is the number of proofs in the array, `Pn` is the size on `N`-th proof in bytes. <br>The maximum number of proofs in the array is 8. The maximum size of each proof is 64 bytes |

## JSON representation of a transaction with data structure v2

```json
{
  "type": 6,
  "version": 2,
  "chainId": 87,
  "senderPublicKey": "9GaQj7gktEiiS1TTTjGbVjU9bva3AbCiawZ11qFZenBX",
  "assetId": "FVxhjrxZYTFCa9Bd4JYhRqXTjwKuhYbSAbD2DWhsGidQ",
  "amount": 9999,
  "fee": 100000,
  "timestamp": 1548660675277,
  "proofs": [
    "61jCivdv3KTuTY6QHgxt4jaGrXcszWg3vb9TmUR26xv7mjWWwjyqs7X5VDUs9c2ksndaPogmdunHDdjWCuG1GGhh"
  ],  
  "id": "csr25XQHT1c965Fg7cY2vJ7XHYVsudPYrUbdaFqgaqL",
  "sender": "3P9QZNrHbyxXj8P9VrJZmVu2euodNtA11UW",
  "height": 1370971
}
```

## Data structure v1

| Field order number | Field name | Field type | Field size in bytes | Field description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Transaction type | Byte | 1 | ID of the transaction type.The value has to be equal to 6 |
| 2 | Sender's public key | Array of bytes | 32 | Public key of the sender's account |
| 3 | Asset ID | Array of bytes | 32 | ID of the asset to be burned |
| 4 | Quantity | Long | 8 | ID of the asset to burn |
| 5 | Fee | Long | 8 | Transaction fee in WAVELET |
| 6 | Timestamp | Long | 8 | Unix time of transaction publication to the network |
| 7 | Signature | Array of bytes | 64 | [Transaction signature](/blockchain/transaction-signature.md) |