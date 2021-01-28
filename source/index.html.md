---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='www.payitgov.com'>PayIt</a>

search: true

code_clipboard: true
---

# Introduction

Welcome to the ChunkyBorgar API! You can use our API and documentation to help you be successful for this exercise.

# Orders

## Get All Orders

```shell
curl "https://raw.githubusercontent.com/MaxBuckley/coeus/api/orders.json"
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
    "customerId": 34114,
    "placedAt": 1580695076000
  }
]
```

This endpoint retrieves all orders.

### HTTP Request

`GET https://raw.githubusercontent.com/MaxBuckley/coeus/api/orders.json`

## Get a Specific Order by Timestamp

```shell
curl "https://raw.githubusercontent.com/MaxBuckley/coeus/api/orders/1580687876000.json"
```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "name": "ChonkyBurger",
    "price": "7.35",
    "customerId": 84210,
    "placedAt": 1580687876000,
    "paymentMethodType": "CREDIT_CARD",
    "paymentAccountId": 128408,
    "paymentStatus": "SUCCESS",
    "storeLocation": {
        "city": "Kansas City",
        "state": "MO",
        "postalCode": "64108"
    }
}
```

This endpoint retrieves a specific order by timestamp.

### HTTP Request

`GET http://maxbuckley.github.io/oreus/orders/{timeStamp}.json"`

### URL Parameters

Parameter | Description
--------- | -----------
Timestamp | The timestamp of the order in GMT epoch milliseconds