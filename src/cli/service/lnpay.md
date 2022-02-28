# LNPAY.co

LNPAY.co is a custodial Bitcoin (BTC) Lightning Wallet.

## Setup

The first step is to create a [lnpay.co](https://lnpay.co) account and obtain a secret API key from the [developers dashboard](https://cloud.lnpay.co/developers/dashboard). Sign-up is currently free and only requires and email address.

Then, add LNPAY.co as a payment service using the command:

```bash
openfare service add lnpay <api-key>
```

## Remove service

Remove the payment service using the command:

```bash
openfare service remove lnpay
```
