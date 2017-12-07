---
title: Crypto Dashboard API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  # - ruby
  # - python
  - javascript

toc_footers:
  # - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

This is the documentation for the backend api implementation for the Crypto Dashboard Project.

# Authentication

> (Not implemented)

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: password"
```

```javascript
const crypto_dash = require('crypto_dash');
let api = crypto_dash.authorize('password');
```

> Make sure to replace `password` with your API key.

Crypto expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: password`

<aside class="notice">
You must replace <code>password</code> with your personal API key.
</aside>

# Balance

## Get Portfolio Balance

```shell
curl "http://example.com/api/balances"
  -H "Authorization: password"
```

```javascript
const crypto_dash = require('crypto_dash');
let api = crypto_dash.authorize('password');
let balance = api.balance.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "BITTREX": [
      {
        "BTC": {
          "amount": 0.1,
          "usd_value": 1500.35
        }
      }
    ]
  },
  {
    "POLONIEX": [
      {
        "BCH": {
          "amount": 0.06441613,
          "usd_value": 86.6437738613641
        }
      },
      {
        "BTC": {
          "amount": 0.05877352,
          "usd_value": 797.4842457738606
        }
      }
    ]
  }
]
```

This endpoint retrieves all exchange balances.

### HTTP Request

`GET http://example.com/api/balances`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
N/A

## Get an Exchange Balance
> (Not implemented)

```shell
curl "http://example.com/api/balances/gdax"
  -H "Authorization: password"
```

```javascript
const crypto_dash = require('crypto_dash');
let api = crypto_dash.authorize('password');
let balance = api.balance.get('gdax');
```

> The above command returns JSON structured like this:

```json
{
    "GDAX": [
        "BTC": {
            "amount": 0.5123,
            "usd_value": 4500.39
        },
        "LTC": {
            "amount": 0.743,
            "usd_value": 120.30
        }
    ]
}
```

This endpoint retrieves an exchange balance.

### HTTP Request

`GET http://example.com/balances/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the exchange

