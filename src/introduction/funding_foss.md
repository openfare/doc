# Funding Free and Open Source Software (FOSS)

The OpenFare Protocol is compatible with every source available software license. This includes the MIT License, Apache licenses, GPL licenses, and so on.

OpenFare lock files are discovered programmatically from within the software dependency tree. This mechanism reveals the demand for funding across the entire software library ecosystem. Donations made using OpenFare reach the roots. It brings to the surface critical software dependencies which are not in the limelight.

OpenFare offers a distributed solution which sidesteps the need for accounts or centralized gatekeepers.

Setting up a project to receive donations is easy. Simply use the `openfare` tool to generate a `OpenFare.lock` file in the project's top level directory.

In this example `OpenFare.lock` file Steve and John split their donations 10/4. John can be paid via PayPal or via the Bitcoin Lightning Network. Steve can only be paid via PayPal:

```json
{
    "plans": {
        "0": {
            "type": "voluntary",
            "payments": {
                "shares": {
                    "steve": "100",
                    "john": "40"
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
                    "keysend": "03488242941915ed5a10151...a55ef4dedf590a7d7dd5"
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
