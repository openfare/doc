# Micropriced Commercial Software

OpenFare can manage payment obligations across thousands of software dependencies. Programmatic management and micropayments means that software maintainers can raise meaningful capital with low prices[^1].



The system:

* payment plans defined in code
* the OpenFare License
* a tool for managing payments across thousands of software dependencies.

The OpenFare License is a lot like the MIT License. The code can be modified, forked, reproduced, executed, and compiled without restriction by anyone. With two exceptions:

1. Commercial users are subject to payment plans defined in code.
2. The license and payment plans can only be modified by the license copyright holder.

The `OpenFare.lock` file defines commercial payment plans for a software package. It is created using the `openfare` tool and is always located next to the project OpenFare `LICENSE` file (usually in the top level directory).

The following example describes a single payment plan. The plan is applicable to commercial organizations which use the software before 2022-12-19 and which have more than 100 employees. It stipulates that this version of the software necessitates a one off payment totalling 20.00 USD. The payment is split 10/4 between Steve and John. John can be paid via PayPal or via the Bitcoin Lightning Network. Steve can only be paid via PayPal.

```json
{
    "plans": {
        "0": {
            "type": "compulsory",
            "conditions": {
                "employees-count": "> 100",
                "current-time": "< 2022-12-19"
            },
            "payments": {
                "total": "20.00 USD",
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
                    "keysend": "03488242941915ed5a101511b8dfeb6db81e0fcd7546f6a55ef4dedf590a7d7dd5"
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

[^1]: Technical lower bound [price](../cli/price.md) as of February 2022: $0.0003788 (USD).
