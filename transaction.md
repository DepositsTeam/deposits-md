
  

Deposits Base  URL in sandbox

```sh
https://api.deposits.dev/api/v1/
```

Deposits Base URL in production

```sh
https://api.deposits.com/api/v1/
```

1. Each of the endpoint below is a `POST` request
2. The endpoints needs the `api_key` and `user_id` as part of the request body
3. `{transaction_id}` is sent as the last segment of the URL
4. For the purpose of this test lets use the sandbox URL

  
#### Transaction states
1. pending: transaction amount has not been credited to a user 
2. active: transaction has been credited to user but pending an internal action
3. refunded: transaction was refunded to sender
4. cancelled: transaction was never credited to receiver but was cancelled before it was sent
5. completed: transaction has been credited and all internal actions completed
6. deactive: transaction was deleted

#### fetch transaction
##### Endpoint

```sh
{baseUrl}/user/get-transaction/{transaction_id}
```
##### Request

```sh
{
	user_id:963
	api_key:cafecito-user
}
```
##### Response

```sh
{
	"status":  "success",
	"message":  "retrieved",
	"data":  {
		"id":  2950,
		"email":  "jeremiah@deposits.com",
		"type":  "credit",
		"transaction_id":  "14476589",
		"beneficiary_name":  "Oniwan Nado",
		"beneficiary_email":  "jeremiah@deposits.com",
		"value":  "120.00",
		"balance":  "7.00",
		"description":  "Wallet topup",
		"status":  "completed",
		"currency":  "usd",
		"reference":  "905",
		"created_at":  "2022-02-25T14:00:03.000000Z"
	}
}
```
#### reverse transaction
##### Endpoint

```sh
{baseUrl}/user/reverse-transaction/{transaction_id}
```  

##### Request

```sh
{
	user_id:963
	api_key:cafecito-user
}
```
##### Response

```sh
{
	"status":  "success",
	"message":  "transaction reversed ",
	"data":  []
}
```
