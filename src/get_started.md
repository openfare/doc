# Get Started

This section describes how to get started with OpenFare. Before getting started, be sure to install the [`openfare` tool](./install.md)

#### Content

- [Fund Public Software Contributors](#fund-public-software-contributors)
- [Get Paid For Contributions](#get-paid-for-contributions)
- [Setup A Project To Receive Funds](#setup-a-project-to-receive-funds)

## Fund Public Software Contributors

OpenFare makes it easy to pay the developers which have contributed to the software you use. 

For example, use the [pay command](./cli/pay.md) in a project directory to donate $1 (USD) to the project's software dependency tree contributors:

```bash
openfare pay 1usd
```

The `pay` command inspects your project's software dependency tree and identifies packages[^1] which support the OpenFare protocol.

## Get Paid For Contributions

A developer's OpenFare profile describes their supported funding mechanism(s). Use the [profile command](./cli/profile.md) to create and manage your profile. For example, add support for receiving funds via the Bitcoin Lightning Network:

```bash
openfare profile add payment-method btc-ln <lnurl>
```

Share your profile via your [GitHub profile repository](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme#prerequisites) or any git repository using the command:

```bash
openfare profile push github.com/<username>
```

Sharing your profile makes it easy for project owners to share their funding with you.

## Setup A Project To Receive Funds

Use the [lock](./cli/lock.md) command to setup your project to receive funds. The command generates a `OpenFare.lock` file which describes how funds are split between the project's contributors.

[^1]: Officially supported package ecosystems can be found [here](./cli/extensions.md).