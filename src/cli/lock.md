# Lock

A project `OpenFare.lock` file describes how funds are distributed between contributors. Here's an example:

```json
{
    "scheme-version": "1",
    "plans": {
        "0": {
            "type": "voluntary",
            "conditions": {},
            "payments": {
                "shares": {
                    "rndhouse": 1000,
                    "steve": 500
                }
            }
        }
    },
    "payees": {
        "rndhouse": {
            "url": "github.com/rndhouse",
            "unique-id": "797f003a-3358-4bd2-bc24-c239ad2bf5de",
            "payment-methods": {
                ...
            }
        },
        "steve": {
            "url": "github.com/steve",
            "unique-id": "888f003a-6658-4pl2-af76-c239ad2bf6fg",
            "payment-methods": {
                ...
            }
        }
    }
}
```

## Creating a lock file

Create a lock file in your project's top level directory:

```bash
openfare lock new
```

## Payment plans

Add a payment plan (donation or fee funded):

```bash
openfare lock add plan compulsory --fee 2usd
```

```bash
openfare lock add plan voluntary
```

## Manage profiles

Add a project contributor profile to the plan:

```bash
openfare lock add profile --url github.com/steve --shares 1000
```

Add your local profile using the command:

```bash
openfare lock add profile --shares 1000
```

## Update

Update a lock file by pulling the latest profile payment methods using the command:

```bash
openfare lock update
```
