---
title: API Reference

search: true
---

# Create New Wallet

> Response

```json
- success
{
    "status": true,
    "data": {
      "address" : "0x2B5C6B3ECC3fC1401A2dAa555537eFC601DE1488",
      "privateKey" : "0x06e350e9e577cf348a9dbdbdd32f2ca5a1dd5ada68b023d2870d940a55b925a7"  
    }
}

- failed
{
  "status": false,
  "message": <Error message>
}
```

### HTTP Request

`POST /wallet/create`


# Get balance by address

> Response

```json
- success
{
    "status": true,
    "data": 20.000423
}

- failed
{
  "status": false,
  "message": <Error message>
}
```

### HTTP Request

`POST /wallet/balances/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
id | required | Client ID
address | optional | Wallet ID
contract | optional | Smart contract address (**only ERC20 tokens**)

# Create new transaction

> Request Parameter Example:

```json
{
  "from": "0x2B5C6B3ECC3fC1401A2dAa555537eFC601DE1488",
  "to": "0x52B6b72d2b6EFc4AC4BE30E42B7b67BB7dc39cdD",
  "privateKey" : "0x06e350e9e577cf348a9dbdbdd32f2ca5a1dd5ada68b023d2870d940a55b925a7",
  "amount": 50,
  "contract": "0x4e005a760e00e17c4912a8070eec047cfecbabbb"
}
```

> Response

```json
- success
{
    "status": true,
    "data": {
        "txid": "70c2e8d3b949f2836e2f3b10d5dd1c240450b7c3f4165c83af314701b005bae6"
    }
}

- failed
{
  "status": false,
  "message": <Error message>
}
```

### HTTP Request

`POST /transaction/create`


### Request Parameters

Parameter | Default | Description
--------- | ------- | -----------
from_address | required | Sender's wallet address
to_address | required | Receiver's wallet address
privateKey | required | Sender's privateKey
amount | required | Amount to send
contract | optional | Smart contract address(**Required for only ERC20 tokens**)