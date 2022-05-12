# Foreign Exchange
These endpoints allow you to create and manage cards.

Please note that;
1. Each of the endpoint below is a `POST` request.
2. The endpoints needs the `api_key` and `user_id` as part of the request body.
3. `{transfer_id}` is sent as the last segment of the URL.
4. The `BaseURL` is the url that gives access to our APIs.

| Environment | Console URL | Base URLs |
| --- | --- | --- |
| Sandbox | https://console.deposits.dev/client-admin/login | https://api.deposits.dev/api/v1/ |
| Production | https://console.deposits.com/client-admin/login | https://api.deposits.com/api/v1/ |



## Get rate
This endpoint gets the exchange rate for specified currencies.               

##### Endpoint
{{BaseURL}}/user/fx/get-rate

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True
|source_currency|String|The currency from which the wire transfer is made.|True
|destination_currency|String|The currency to which the wire transfer should be made.|True

##### Response
```
{
    "status": "success",
    "message": "Fx transfer rate retrieved",
    "data": {
        "rate": 1.51528,
        "source_currency": "USD",
        "destination_currency": "GBP"
    }
}
```


## Enrol a user for FX
This endpoint permits a user to perform foreign exchange transactions.               

##### Endpoint
{{BaseURL}}/user/fx/enroll-user-for-fx

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True
|address_1|String| |True
|city|String| |True
|state|String| |True
|postal_code|String| |True
|date_of_birth|String|The user’s date of birth in the format DD-MM-YYYY.|True
|phone_number|String| |True

##### Response
```
{
    "status": "success",
    "message": "User enrolled for FX",
    "data": []
}
```


## Get wallets
This endpoint retrieves the balance of the user's wallets.

##### Endpoint
{{BaseURL}}/api/v1/user/fx/get-wallets

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True

##### Response
```
{
    "status": "success",
    "message": "User FX wallets",
    "data": [
        {
            "currency": "USD",
            "balance": "0",
            "available_balance": "0"
        }
    ]
}
```

## Get wallet funding info
This endpoint retrieves the details the user can use to fund the wallet.

##### Endpoint
{{BaseURL}}/user/fx/get-wallet-funding-info

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True

##### Response
```
{
    "status": "success",
    "message": "User FX wallet funding instruction",
    "data": [
        {
            "type": "transfer_only",
            "currency": null,
            "bank_name": null,
            "bank_address1": null,
            "bank_city": null,
            "bank_state_province_region": null,
            "bank_postal_code": null,
            "bank_country": null,
            "account_number": null,
            "routing_code": null,
            "swift_bic": null
        }
    ]
}
```


## Save a wire account
This endpoint saves a wire account for transactions.               

##### Endpoint
{{BaseURL}}/user/fx/save-wire-account

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True
|swift|Integer|Swift code of the bank.|True
|iban|String|IBAN code provided by the user.|True
|bank_name|String|Name of bank provided by the user.|True
|account_name|String|Account name at the specified bank.|True
|routing_number|Integer|Bank routing number.|True
|currency|String|The currency of the bank account provided.|True
|postal_code|String| |True
|state|String| |True
|city|String| |True
|country|String| |True
|address_1|String| |True

##### Response
```
{
    "status": "success",
    "message": "User Beneficiary created for FX",
    "data": []
}
```


## Get wire accounts
This endpoint retrieves all the wire accounts saved by the user.

##### Endpoint
{{BaseURL}}/user/fx/get-wire-accounts

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True

##### Response
```
{
    "status": "success",
    "message": "User Accounts retrieved for FX",
    "data": {
        "current_page": 1,
        "data": [
            {
                "id": 69,
                "type": "wire",
                "bank": "GNS Bank",
                "account_name": "Jina niko",
                "iban": "00000002",
                "swift": "CITIUS12",
                "routing_number": "113596002",
                "zip_code": "23233",
                "address": "kojo close st dan avenue",
                "city": "Bridge city",
                "state": "Ohio",
                "country": "US",
                "account_type": null,
                "created_at": "2022-05-07T17:23:57.000000Z",
                "updated_at": "2022-05-07T17:23:57.000000Z"
            },
            {
                "id": 67,
                "type": "wire",
                "bank": "GNS Bank",
                "account_name": "Jina niko",
                "iban": "3530142019955809",
                "swift": "101112842",
                "routing_number": "12345678",
                "zip_code": "500272",
                "address": "kojo close st dan avenue",
                "city": "Bridge city",
                "state": "Ohio",
                "country": "US",
                "account_type": null,
                "created_at": "2022-05-07T07:43:07.000000Z",
                "updated_at": "2022-05-07T07:43:07.000000Z"
            }
				]
		}
}
```


## Create wire transfer
This endpoint creates a wire transfer.

##### Endpoint
{{BaseURL}}/user/fx/create-transfer

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True
|account_id|Integer|The id attached to the saved wire account.|True
|amount|Integer|The amount to be tranferred.|True
|description|String|Transfer description.|True
|source_currency|String|The currency from which the wire transfer is made.|True
|destination_currency|String|The currency to which the wire transfer should be made.|True

##### Response
```
{
    "status": "success",
    "message": "Fx transfer created for Beneficiary, please check for the transfer rate next",
    "data": {
        "id": 567,
        "email": "calmpress+four-cafe@gmail.com",
        "from_currency": null,
        "to_currency": "GBP",
        "amount": "1",
        "description": "for school fees",
        "transaction_id": "7c7c7de0db52825",
        "reference": "4f0fbce5-f410-4578-ab95-258b5dd70bf0",
        "account": {
            "id": 71,
            "type": "wire",
            "bank": "GNS Bank",
            "account_name": "Jina niko",
            "iban": "00000001",
            "swift": "CITIUS12",
            "routing_number": "113596002",
            "zip_code": "23233",
            "address": "kojo close st dan avenue",
            "city": "Bridge city",
            "state": "Ohio",
            "country": "US",
            "account_type": null,
            "created_at": "2022-05-09T20:41:24.000000Z",
            "updated_at": "2022-05-09T20:41:24.000000Z"
        },
        "status": "pending",
        "created_at": "2022-05-09T21:13:59.000000Z",
        "updated_at": "2022-05-09T21:14:07.000000Z"
    }
}
```


## Get wire transfer rate
This endpoint retrieves the exchange rate at which a wire transfer was made.

##### Endpoint
{{BaseURL}}/user/fx/get-transfer-rate/{transfer_id}

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True
|transfer_id|Integer|The id attached to the wire transfer.|True

##### Response
```
{
    "status": "success",
    "message": "Fx transfer rate retrieved, if you are ok with it, kindly authorize this payout",
    "data": {
        "rate": 0.9229350000000001,
        "source_amount": "1",
        "destination_amount": 0.9229350000000001
    }
}
```


## Authorize Wire Transfer
This endpoint authorizes a wire transfer.

##### Endpoint
{{BaseURL}}/user/fx/authorize-transfer/{transfer_id}

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True
|transfer_id|Integer|The id attached to the wire transfer.|True

##### Response
```
{
    "status": "success",
    "message": "Fx transfer sent to que",
    "data": {
        "id": 567,
        "email": "calmpress+four-cafe@gmail.com",
        "from_currency": null,
        "to_currency": "GBP",
        "amount": "1",
        "description": "for school fees",
        "transaction_id": "7c7c7de0db52825",
        "reference": "4f0fbce5-f410-4578-ab95-258b5dd70bf0",
        "account": {
            "id": 71,
            "type": "wire",
            "bank": "GNS Bank",
            "account_name": "Jina niko",
            "iban": "00000001",
            "swift": "CITIUS12",
            "routing_number": "113596002",
            "zip_code": "23233",
            "address": "kojo close st dan avenue",
            "city": "Bridge city",
            "state": "Ohio",
            "country": "US",
            "account_type": null,
            "created_at": "2022-05-09T20:41:24.000000Z",
            "updated_at": "2022-05-09T20:41:24.000000Z"
        },
        "status": "active",
        "created_at": "2022-05-09T21:13:59.000000Z",
        "updated_at": "2022-05-09T21:21:54.000000Z"
    }
}
```


## Get wire transfers
This endpoint retrieves all the wire transfers performed by a user.

##### Endpoint
{{BaseURL}}/user/fx/get-transfers

##### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|True
|user_id|Integer|The user_id of the current user.|True

##### Response
```
{
    "status": "success",
    "message": "User Transfers retrieved",
    "data": {
        "current_page": 1,
        "data": [
            {
                "id": "370",
                "email": "calmpress+four-cafe@gmail.com",
                "amount": "1.00",
                "currency": "usd",
                "transaction_id": "7eeb4209044e5e8",
                "reference": null,
                "description": "for school fees",
                "account": {
                    "id": 69,
                    "user_id": "370",
                    "email": "calmpress+four-cafe@gmail.com",
                    "type": "wire",
                    "account_name": "Jina niko",
                    "account_number": null,
                    "currency": null,
                    "zip": "23233",
                    "city": "Bridge city",
                    "state": "Ohio",
                    "country": "US",
                    "iban": "00000002",
                    "swift": "CITIUS12",
                    "address": "kojo close st dan avenue",
                    "routing_number": "113596002",
                    "tax_id": null,
                    "coin_address": null,
                    "bank": "GNS Bank",
                    "account_type": null,
                    "sec": null,
                    "status": "pending",
                    "created_at": "2022-05-07T17:23:57.000000Z",
                    "updated_at": "2022-05-07T17:23:57.000000Z",
                    "privacy_token": null,
                    "account_limit": 0,
                    "daily_limit": 0,
                    "monthly_limit": 0
                },
                "status": "pending",
                "created_at": "2022-05-07T21:43:32.000000Z",
                "updated_at": "2022-05-07T21:43:32.000000Z"
            },
            {
                "id": "370",
                "email": "calmpress+four-cafe@gmail.com",
                "amount": "1.00",
                "currency": "usd",
                "transaction_id": "8372d8b6eeea556",
                "reference": null,
                "description": "for school fees",
                "account": {
                    "id": 69,
                    "user_id": "370",
                    "email": "calmpress+four-cafe@gmail.com",
                    "type": "wire",
                    "account_name": "Jina niko",
                    "account_number": null,
                    "currency": null,
                    "zip": "23233",
                    "city": "Bridge city",
                    "state": "Ohio",
                    "country": "US",
                    "iban": "00000002",
                    "swift": "CITIUS12",
                    "address": "kojo close st dan avenue",
                    "routing_number": "113596002",
                    "tax_id": null,
                    "coin_address": null,
                    "bank": "GNS Bank",
                    "account_type": null,
                    "sec": null,
                    "status": "pending",
                    "created_at": "2022-05-07T17:23:57.000000Z",
                    "updated_at": "2022-05-07T17:23:57.000000Z",
                    "privacy_token": null,
                    "account_limit": 0,
                    "daily_limit": 0,
                    "monthly_limit": 0
                },
                "status": "pending",
                "created_at": "2022-05-07T21:43:16.000000Z",
                "updated_at": "2022-05-07T21:43:16.000000Z"
            }
        ]
    }
}
