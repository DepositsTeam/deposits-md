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

When the add card button is clicked or on your add card screen you have to call the deposits API in the format below and ensure you pass the right entity_type and the right entity_id and the URL has to be opened in a webview.

```sh
{baseUrl}/connect/save-entity-card/{type}/{type_id}
```

```sh
{type} is the type of entity and is either user or business
```

```sh
{type_id} is the id of the entity and is either user_id or business_id
```

The card entered here will be saved in deposits for that entity, depending on if the process was successful you would see a success response on the screen or details of the error encountered, the modal should be closed manually.


