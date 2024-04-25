# Deposits Astra: Create User in Astra through Deposits

## _How to implement add user to astra on web/mobile via the API_


baseUrl for the Deposits API in sandbox
```sh
https://api.deposits.dev
```
baseUrl for the Deposits API in production
```sh
https://api.ondeposits.com
```

## _Web_/_Mobile_

When one needs to a user in Astra you have to call the deposits API in the format below and ensure you pass the right entity_type and the right entity_id and the URL has to be opened in a webview.

```sh
{baseUrl}/connect/astra-authorize-user/{type}/{type_id}
```

```sh
{type} is the type of entity and is either user or business
```

```sh
{type_id} is the id of the entity and is either user_id or business_id
```

The User will be created in astra and the USER_ID saved in deposits, depending on if the process was successful you would see a success response on the screen or details of the error encountered, the modal should be closed manually.


