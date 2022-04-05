# Lock File

Lock files define donation/fee payment plans for software packages. They also describe payees and their preferred payment methods.

A lock file is constructed using the `openfare` tool. Command line interface documentation for creating and managing a lock file can be found [here](../cli/lock.md).

Lock files are always located in the package's top level directory as `OpenFare.lock`.

## Overview

A lock file is composed of payment plans and payees:

```json
{
    "plans": {
        ...
    },
    "payees": {
        ...
    }
}
```

### Payment Plans

A lock file can contain multiple payment plans. A payment plan describes the following:

* how funds should be split between payees
* conditions used to determine applicability
* and a total fee for `compulsory` plans.

#### Example

```json
"plans": {
    "0": {
        "type": "compulsory",
        "conditions": {
            "for-profit": "true",
            "employees-count": "> 100",
            "expiration": "2022-12-19"
        },
        "payments": {
            "total": "0.0025 USD",
            "shares": {
                "steve": 100,
                "john": 40
            }
        }
    },
    "1": {
        "type": "voluntary",
        "conditions": {
            "expiration": "2022-12-19"
        },
        "payments": {
            "shares": {
                "steve": "100",
                "john": "40"
            }
        }
    }
}
```

#### Conditions

A payment plan is deemed applicable to a software library user based on plan `conditions`. Conditions are evaluated programmatically in conjunction with a user's configuration settings.

For example, the `expiration` condition invalidates a plan at any time beyond the associated date value.

Compulsory payment plan "0" from the example above stipulates three conditions. The plan is applicable to for-profit organizations which use the software before 2022-12-19 and which have more than 100 employees. Conditions are logic-AND chained together.

#### Payments

Shares are allocated by payee labels (`steve` and `john` in the example above). These labels refer to payees within the lock file's `payees` section. Shares determine the proportion of funds received by each payee.

### Payees

The `payees` section of a lock file describes payees and their supported payment methods for receiving funds.

Here's an example:

```json
"payees": {
    "john": {
        "url": "github.com/john",
        "unique-id": "797f003a-3358-4bd2-bc24-c239ad2bf5de",
        "payment-methods": {
            "btc-lightning": {
                "lnurl": "03488242941915ed5a10151...a55ef4dedf590a7d7dd5"
            }
        }
    },
    ...
}
```

Field descriptions: 

* `url` - Payee's OpeFare profile URL for pulling profile updates.
* `unique-id` - Helper (not security critical) field to ensure lock file payee labels are unique and to simplify mapping between local and remote profiles.
* `payment-methods` - Supported payment methods for receiving funds.
