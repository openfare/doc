# Extensions

Extensions allow the `openfare` tool to interact with package registries and ecosystems. For example, the [openfare-js](https://github.com/openfare/openfare-js) extension allows `openfare` to find [lock files](./lock.md) within [npmjs.com](https://npmjs.com) packages.

#### Official extensions

| Name                                                        | Ecosystem      | Package Registries |
|-------------------------------------------------------------|----------------|--------------------|
| [openfare-js](https://github.com/openfare/openfare-js)      | Javascript     | npmjs.com          |

## Add extension

The `openfare-js` extension is included with `openfare` out of the box. Other extensions can be added using the command:

```bash
openfare extensions add <repository_url_or_name>
```

### Examples

Add via repository URL:

```bash
openfare extensions add https://github.com/openfare/openfare-py
```

Add via extension name:

```bash
openfare extensions add py
```

`openfare` will search for the latest extension release at address:

```url
https://github.com/openfare/openfare-{name}
```

## Disable extension

Extensions can be disabled without deletion (config file retained) using the command:

```bash
openfare extensions disable py
```

## Enable extension

Disabled extensions can be enabled using the command:

```bash
openfare extensions enable py
```

## Removing extension

Extensions can be disabled and deleted using the command:

```bash
openfare extensions remove py
```
