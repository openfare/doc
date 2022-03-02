# Profile

Your OpenFare profile describes how you can receive funds. Here's an example:

```json
{
  "openfare-profile": {
    "unique-id": "797f003a-3358-4bd2-bc24-c239ad2bf5de",
    "payment-methods": {
      "btc-lightning": {
          "lnurl": "LNURL1DP68GURN8GHJ7CMVDA6K...23JS3YTAFK"
      }
    }
  }
}
```

## Payment methods

Add payment methods to your profile:

```bash
openfare profile add payment-method btc-ln <lnurl>
```

### Setup via services

Some services can be used to setup payment methods, for example:

```bash
openfare profile add payment-method btc-ln --service lnpay
```

## Share

Sharing your profile allows other users to programmatically discover how you can be paid. Project [lock files](./lock.md) can then be curated and updated by pulling in your latest profile payment methods.

Use the `push` subcommand to share your profile:

```bash
openfare profile push <url>
```

Where `url` is any Git repository or GitHub user profile URL (`github.com/<username>`).
