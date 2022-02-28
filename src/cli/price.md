# Price

Commercial users of OpenFare Licensed software are subject to payment plans. Use the `price` command to get a breakdown of costs for a project's software dependency tree.

```bash
openfare price <package-name> <package-version>
```

Software priced using `openfare` can cost less than a cent. This is because `openfare` converts payments into satoshis (SATS) which is the smallest bitcoin denomination. 100 million SATS make up a single bitcoin.

There are 2608 SATS in $1.00 (USD) as of February 2022. Which implies a technical lower limit software price of $0.0003788!

#### -e, --extension

Specify an extension to differentiate between package registries/ecosystems. Example:

```bash
--extension js
```

## Example

```bash
openfare price is-even
```

Output:

```text
Registry: npmjs.com
Total: 0.001 USD
   name    | version | price (USD) | notes 
-----------+---------+-------------+---------------------
 is-even   | 1.0.0   |      -      |  
           |         |             |    
 is-buffer | 1.1.6   |      -      |  
 is-number | 3.0.0   |    0.001    | employees-count > 100
 is-odd    | 0.1.2   |      -      |  
 kind-of   | 3.2.2   |      -      |     
```
