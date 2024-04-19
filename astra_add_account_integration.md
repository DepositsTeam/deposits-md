# Deposits Astra: Save Account using Astra-Plaid through Deposits

## _How to implement saving user account to astra on web/mobile via the API_


baseUrl for the Deposits API in sandbox
```sh
https://api.deposits.dev
```
baseUrl for the Deposits API in production
```sh
https://api.ondeposits.com
```

## _Web_/_Mobile_

When one needs to a save an account for a user in Astra you have to call the deposits API in the format below and ensure you pass the right entity_type and the right entity_id and the URL has to be opened in a webview.

```sh
{baseUrl}/api/v2/connect/astra-plaid-link-account/{type}/{type_id}
```

```sh
{type} is the type of entity and is either user or business
```

```sh
{type_id} is the id of the entity and is either user_id or business_id
```
This will take you through the Plaid interface were the bank will be selected, internet banking login and bank account selected.
The Account will be saved in astra and the ACCOUNT_ID saved in deposits, depending on if the process was successful you would see a success response on the screen or details of the error encountered, the modal should be closed manually.


