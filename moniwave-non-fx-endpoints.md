## Non FX Endpoints

| Environment | Console URL | Base URLs |

| --- | --- | --- |

| Sandbox | https://console.deposits.dev/client-admin/login | https://api.deposits.dev/api/v1/ |

| Production | https://console.deposits.com/client-admin/login | https://api.deposits.com/api/v1/ |

## transfer funds

This endpoint is used to transfer funds(usd) from one user to another within the same tenant.

##### Endpoint

```

{{BaseURL}}/user/transfer-funds

```

##### Parameters

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

|receiver_id|String|id of the receiver.|True

|amount|String|The amount to be transfered.|True

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

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

|amount|String| |True

|description|String| |True

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

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

|amount|String| |True

|description|String| |True

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

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

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

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

|amount|String|Swift code of the bank.|True

|account_id|String||True

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

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

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

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|String|The user_id of the current user.|True

|routing_number|String||True

|account_number|String||True

|account_name|String||True

|bank_name|String||True

|account_type|String|checking, savings|True

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

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

|routing_number|String||True

|account_number|String||True

|account_name|String||True

|bank_name|String||True

|account_type|String|checking, savings|True

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

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

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

{{BaseURL}}/user/verify-bank-account/919

```

##### Parameters

|Parameters |Type |Description |Required

--- | --- | ---| ---|

|api_key|String|A unique identifier used to authorize access to your project.|True

|user_id|Integer|The user_id of the current user.|True

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
