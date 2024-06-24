# Deposits Save Card UI

## _How to implement save card UI on web/mobile 


baseUrl for the Deposits API in sandbox
```sh
https://api.deposits.dev
```
baseUrl for the Deposits API in production
```sh
https://api.ondeposits.com
```

## _Web_/_Mobile_

When the add bank account button is clicked or on your add bank account screen you have to call the deposits API in the format below and ensure you pass the right entity_type and the right entity_id and the URL has to be opened in a webview.

```sh
{baseUrl}/connect/save-entity-bank-account/{type}/{type_id}
```

```sh
{type} is the type of entity and is either user or business
```

```sh
{type_id} is the id of the entity and is either user_id or business_id
```

The bank account selected from any of the providers here will be saved in deposits for that entity, depending on if the process was successful you would see a success response on the screen or details of the error encountered, the modal should be closed manually.

Note: Listen for the closePage event on the frontend and close the iframe when received