# Pay

The pay command uses a [payment service](./service) to pay donations or fees to software dependency tree contributors.

```bash
openfare pay <donation>
```

#### --service

Specify payment service for sending payment.

#### --default

Set specified payment service as default.

### Donations

Donations made via the `pay` command are divided equally between dependency tree packages. Package sums are then split per contributor based on [payment plan shares](./lock.md).

For example, running the following command in a project directory donates $1 (USD) to the project's software dependency tree contributors:

```bash
openfare pay 1usd
```

Hundreds if not thousands of developers might have contributed the software which makes up a dependency tree. `openfare` converts a $1 donation into satoshis (SATS) which is the smallest bitcoin denomination. 100 million SATS make up a single bitcoin. This means that each contributor will likely receive some fraction of the total donation.
