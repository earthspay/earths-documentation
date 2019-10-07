# Earths Payments API

If you want to make someone pay with EARTHS or any other Earths tokens, you can use our Payments API.

## Process

1. You need to set up a button on your site which triggers the creation of an URL and a redirect to it.
2. A user decides to buy something and the user presses that button.
3. After that, the user is redirected to the Earths Client with a payment parameters window.
4. The user modifies those parameters if possible and submits the form.
5. If everything's okay, The user is redirected back to referer.
6. Referer is provided with transaction ID which can be checked if it's in the blockchain.

If the user interrupts the process, he stays on the Earths Client page.

## Details

[**Here**](https://demo.earths.ga/payment-api) you can find the demo project which shows how to use Payment API for donations. The Payment API allows creating a special link for avoiding users' seed input on 3-party sites.

### Request

[Example](https://client.earths.ga/#send/EARTHS?recipient=your-alias&amount=0.01&attachment=SomeString&referrer=https://example.com&strict): `https://client.earths.ga/#send/EARTHS?recipient=your-alias&amount=0.01&attachment=SomeString&referrer=https://example.com&strict`.

Basic path is `https://client.earths.ga/#send/{assetId}`. Then there are the parameters.

#### Asset ID

`/#send/8LQW8f7P5d5PZM7GtZEBgaqRPGSzS3DfPuiXrURJ4AJS` — the ID of the asset needed for the payment. The only path parameter here. _\(Required\)_

#### Recipient

`?recipient=3PCAB4sHXgvtu5NPoen6EXR5yaNbvsEA8Fj` — the address \(or an alias\) to send tokens to. 

#### Amount

`?amount=10.5` — the number of tokens to pay. _\(Required\)_

#### Attachment

`?attachment=SomeString` — payment attachment string. _\(Optional\)_

#### Referrer

`?referrer=https://example.com/earths-payment` — the URL of your service. It should be HTTPS-only. _\(Optional\)_

#### Strict mode

`?strict` — if this flag is set, a user won't be able to change the data in the form. _\(Optional\)_

### Response

Example: `https://example.com/earths-payment?txId=D1USZfZPzVd2XNH9xj52Z81XhxChpwUKDJpQHz2haXRT`.

The ID of the user's payment transaction will be in the query.

#### Transaction ID

`?txId=D1USZfZPzVd2XNH9xj52Z81XhxChpwUKDJpQHz2haXRT` — the ID of user's successful transaction.