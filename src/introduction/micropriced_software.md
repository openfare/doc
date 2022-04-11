# Micropriced Software

OpenFare can manage payment obligations across thousands of software dependencies. Programmatic management and micropayments means that public software contributors can raise meaningful capital with low prices[^1].

`openfare` detects applicable fees across a project's entire software dependency tree. Thousands of micro-fees can be consolidated into a single lump sum using OpenFare compatible payment [services](../concepts/services.md). These services take on the complexities of distributing funds to public software contributors based on lock file payment plans.

## Fee Funded Payment Plans

Payment plans for fee funded software are defined in the package [lock](../concepts/lock.md) files.

The following example describes a single payment plan. The plan is applicable to for-profit organizations which use the software before 2022-12-19 and which have more than 100 employees. It stipulates that this version of the software necessitates a one off payment totalling 0.0025 USD. The payment is split 10/4 between Steve and John. John can be paid via the Bitcoin Lightning Network. Steve can only be paid via PayPal.

```json
{
    "plans": {
        "0": {
            "type": "compulsory",
            "conditions": {
                "for-profit": "true",
                "employees-count": "50 <= count < 150",
                "expiration": "2022-12-19"
            },
            "payments": {
                "total": "0.0025 USD",
                "shares": {
                    "steve": 100,
                    "john": 40
                }
            }
        }
    },
    "payees": {
        "john": {
            "payment-methods": {
                "paypal": {
                    "email": "john@example.com"
                },
                "btc-lightning": {
                    "lnurl": "03488242941915ed5a101511b8dfeb6db81e0fcd7546f6a55ef4dedf590a7d7dd5"
                }
            }
        },
        "steve": {
            "payment-methods": {
                "paypal": {
                    "email": "steve@example.com"
                }
            }
        }
    }
}
```

## Pricing Software Packages

Specific packages or a project's software dependency tree can be priced using the [price](../cli/price.md) command.

[^1]: Technical lower bound [price](../cli/price.md) as of February 2022: $0.0003788 (USD).
