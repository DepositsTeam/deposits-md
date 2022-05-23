## Non FX Endpoints

Please note that;
1. Each of the endpoint below is a `POST` request.
2. The endpoints needs the `api_key` and `user_id` as part of the request body.
3. `{transfer_id}` is sent as the last segment of the URL.
4. The `BaseURL` is the url that gives access to our APIs.


Deposits Base  URL in sandbox

```sh
https://api.deposits.dev/api/v1/
```

Deposits Base URL in production

```sh
https://api.deposits.com/api/v1/
```

## transfer funds

This endpoint is used to transfer funds(usd) from one user to another within the same tenant.

##### Endpoint

```

{{BaseURL}}/user/transfer-funds

```

##### Parameters

```
user_id:343
api_key:cafecito-user
receiver_id:375
amount:1.1
```

##### Response

```

{

"status":  "success",

"message":  "Transfer successful",

"data":  []

}

```

## Debit a user

This endpoint debits a user and credits the funds to the Master wallet(Funding Account).

##### Endpoint

```

{{BaseURL}}/user/debit-user-wallet

```

##### Parameters

```
user_id:343
api_key:cafecito-user
amount:1.1
description:wired out
```

##### Response

```

{

"status":  "success",

"message":  "user wallet debit successful",

"data":  []

}

```

## Credit a user

This endpoint credits a user and debits the Master wallet(Funding Account).

##### Endpoint

```

{{BaseURL}}/user/credit-user-wallet

```

##### Parameters

```
user_id:343
api_key:cafecito-user
amount:1.1
description:wired in
```

##### Response

```

{

"status":  "success",

"message":  "user wallet credit successful",

"data":  []

}

```

## Get Withdrawals

This endpoint retrieves the withdrawals/transfers of a user both ACH and Wire.

##### Endpoint

```

{{BaseURL}}/user/get-withdrawals

```

##### Parameters

```
user_id:343
api_key:cafecito-user
```

##### Response

```

{

"status": "success",

"message":  "withdrawals retrieved ",

"data":  [

{

"id":  "3",

"email":  "calmpress@gmail.com",

"amount":  "1.00",

"currency":  "usd",

"transaction_id":  "13e9f",

"reference":  null,

"description":  "funds transfer to account",

"account_name":  "jine deli",

"account_number":  "212121222",

"bank":  "GS bank",

"routing_number":  "4883488438",

"status":  "pending",

"created_at":  "2021-05-04T21:22:14.000000Z",

"update_at":  null

},

{

"id":  "3",

"email":  "calmpress@gmail.com",

"amount":  "1.00",

"currency":  "usd",

"transaction_id":  "0efc2",

"reference":  null,

"description":  "wallet withdrawal",

"account_name":  "Plaid Checking",

"account_number":  "1111222233330000",

"bank":  "CITIZENS BANK NA",

"routing_number":  null,

"status":  "completed",

"created_at":  "2021-05-04T21:20:41.000000Z",

"update_at":  null

},

{

"id":  "3",

"email":  "calmpress@gmail.com",

"amount":  "0.00",

"currency":  "usd",

"transaction_id":  "HDJW44344343jkfdjkvd",

"reference":  null,

"description":  "send",

"account_name":  "James David",

"account_number":  "33fQ8Qc2hQRuL3Z1JZTyXmDmjiF71ow5Z3",

"bank":  "ABC Bank",

"routing_number":  null,

"status":  "pending",

"created_at":  "2019-05-01T17:43:50.000000Z",

"update_at":  null

},

]

}

```

## Withdraw

This endpoint allows a user withdraw funds to either an ACH/Wire bank account.

##### Endpoint

```

{{BaseURL}}/user/withdraw

```

##### Parameters

```
api_key:cafecito-user
user_id:343
amount:1.2
account_id:25
```

##### Response

```

{

"status": "success",

"message":  "Withdrawal ",

"data":  {

"user_id":  3,

"email":  "calmpress@gmail.com",

"type":  "withdrawal",

"currency":  "usd",

"amount":  "1",

"description":  "wallet withdrawal",

"transaction_id":  "0efc2",

"account_name":  "Plaid Checking",

"account_number":  "342233322333",

"bank":  "CITIZENS BANK NA",

"account_id":  6,

"status":  "pending",

"updated_at":  "2021-05-04T21:20:41.000000Z",

"created_at":  "2021-05-04T21:20:41.000000Z",

"id":  523

}

}

```

## Get ACH accounts

This endpoint retrieves all the ACH accounts saved by the user.

##### Endpoint

```

{{BaseURL}}/user/get-banks

```

##### Parameters

```
user_id:343
api_key:cafecito-user
```

##### Response

```

{

"status": "success",

"message":  "Bank Accounts retrieved",

"data":  {

"current_page":  1,

"data":  [

{

"id":  959,

"account_holder_name":  "Jina niko",

"account_number":  "353014201995580",

"routing_number":  "101112842",

"bank_name":  "GNS Bank",

"account_type":  "CHECKING",

"status":  "pending",

"created_at":  "2022-04-25T13:54:19.000000Z",

"updated_at":  "2022-04-25T13:54:19.000000Z"

},

{

"id":  958,

"account_holder_name":  "Jina niko",

"account_number":  "353014201995580",

"routing_number":  "101112842",

"bank_name":  "GNS Bank",

"account_type":  "CHECKING",

"status":  "pending",

"created_at":  "2022-04-25T13:53:00.000000Z",

"updated_at":  "2022-04-25T13:53:00.000000Z"

}

],

"first_page_url":  "{{BaseURL}}/user/get-banks?page=1",

"from":  1,

"last_page":  3,

"last_page_url":  "{{BaseURL}}/user/get-banks?page=3",

"next_page_url":  "{{BaseURL}}/user/get-banks?page=2",

"path":  "{{BaseURL}}/user/get-banks",

"per_page":  10,

"prev_page_url":  null,

"to":  10,

"total":  25

}
}

```

## Add ACH Bank account

This endpoint adds an ACH bank account for a user.

##### Endpoint

```

{{BaseURL}}/user/add-bank

```

##### Parameters

```
user_id:963
api_key:cafecito-user
routing_number:101112842
account_number:353014201995580
account_name:Jina niko
bank_name:GNS Bank
account_type:checking
```

##### Response

```

{

"status": "success",

"message":  "Bank Account saved",

"data":  {

"id":  959,

"account_holder_name":  "Jina niko",

"account_number":  "353014201995580",

"routing_number":  "101112842",

"bank_name":  "GNS Bank",

"account_type":  "CHECKING",

"status":  "pending",

"created_at":  "2022-04-25T13:54:19.000000Z",

"updated_at":  "2022-04-25T13:54:19.000000Z"

}

}

```

## Update bank account

This endpoint retrieves the exchange rate at which a wire transfer was made.

##### Endpoint

```

{{BaseURL}}/user/update-bank/{account_id}

```

##### Parameters

```
user_id:963
api_key:cafecito-user
routing_number:101112842
account_number:353014201995580
account_name:Jina nikon
bank_name:GNS Bank
account_type:checking
```

##### Response

```

{

"status": "success",

"message":  "Bank Account updated",

"data":  {

"id":  919,

"account_holder_name":  "Jina nikon",

"account_number":  "353014201995580",

"routing_number":  "101112842",

"bank_name":  "GNS Bank",

"account_type":  "CHECKING",

"status":  "pending",

"created_at":  "2022-02-24T12:56:50.000000Z",

"updated_at":  "2022-04-25T13:57:23.000000Z"

}

}

```

## Delete a bank account

This endpoint deletes a bank account.

##### Endpoint

```

{{BaseURL}}/user/delete-bank/{account_id}

```

##### Parameters

```
user_id:963
api_key:cafecito-user
```

##### Response

```

{

"status": "success",

"message":  "Bank Account deleted",

"data":  []

}

```

## Verify Bank Account

This endpoint verifies a bank account via micro deposits, some funds was sent to

##### Endpoint

```

{{BaseURL}}/user/verify-bank-account/{account_id}

```

##### Parameters

```
user_id:963
api_key:cafecito-user
deposit_one:1
deposit_two:1
```

##### Response

```

{

"status": "success",

"message":  "Bank account verified successfully",

"data":  {

"id":  906,

"type":  "fiat",

"bank":  "GNS Bank",

"account_name":  "Jina niko",

"account_type":  "CHECKING",

"account_number":  "353014201995580",

"routing_number":  "101112842",

"account_limit":  null,

"status":  "completed",

"account_owner_name":  "Nado,Oniwan",

"account_owner_email":  "jeremiah@deposits.com",

"account_owner_phone":  "192343234",

"created_at":  "2022-02-13T19:14:40.000000Z"

}

}

```
