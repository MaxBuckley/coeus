---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='www.payitgov.com'>PayIt</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to the ChunkyBorgar API! You can use our API and documentation to help you be successful for this exercise.

The goal of this exercise is to provide some exposure to some processes we have here at PayIt and also simplified versions of some of the problems have to solve.

# Exercise

A ChonkyBorgar order has been placed however the payment failed and will need to be resubmitting using this API, however it's not entirely finished yet and some additions may need to be made.

## 1
An order was placed on 02/02/2020 at 09:16 PM Central Standard Time. Funds were never collected for the order, so we're needing look up the order and submit a transaction.
# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Orders

## Get All Orders

```shell
curl "http://maxbuckley.github.io/oreus/orders"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "ChonkyBurger",
    "price": "7.35",
    "customerId": 84210,
    "placedAt": 1580687876000
  },
  {
    "id": 2,
    "name": "VegemiteBurger",
    "price": "6.95",
    "customerId": 1580695076000
  }
]
```

This endpoint retrieves all orders.

### HTTP Request

`GET http://maxbuckley.github.io/oreus/orders`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Order by Timestamp

```shell
curl "http://maxbuckley.github.io/oreus/orders/{timeStamp}"
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
  "name": "ChonkyBurger",
  "price": "7.35",
  "customerId": 84210,
  "placedAt": 1580687876000
}
```

This endpoint retrieves a specific order.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://maxbuckley.github.io/oreus/orders/{timeStamp}"`

### URL Parameters

Parameter | Description
--------- | -----------
Timestamp | The timestamp of the order in GMT epoch milliseconds

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

