# Config

Modify config variables using the command:

```bash
openfare config set <field-path> <field-value>
```

Show config values (as JSON) using the command:

```bash
openfare config show <field-path>
```

### Example config file

```json
{
  "core": {
    "preferred-currency": "USD"
  },
  "services": {
    "default": "lnpay",
    "portal": {
      "url": "http://openfare.dev/",
      "api-key": "<key>",
      "email": null
    },
    "lnpay": {
      "secret-api-key": "<key>"
    }
  },
  "profile": {
    "url": "github.com/rndhouse",
    "employees-count": null,
    "for-profit": false,
    "include-voluntary-donations": true
  },
  "extensions": {
    "enabled": {
      "js": true
    },
    "registries": {
      "npmjs.com": "js"
    }
  }
}
```
