# Card Issuing

These endpoints allow you to create and manage cards.

Please note that;
1. Each of the endpoint below is a `POST` request.
2. The endpoints needs the api_key and user_id as part of the request body.
3. `{card_id}` is sent as the last segment of the URL.
4. For the purpose of this test lets use the sandbox URL.


## Create a card
This endpoint creates a virtual card.

#### Endpoint
```
{{BaseURL}}/user/create-card
```

#### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Yes
|user_id|Integer|The user_id of the current user|Yes


## Get cards
This endpoint retrieves all the user’s virtual cards.

#### Endpoint
```
{{BaseURL}}/user/get-cards
```

#### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Yes
|user_id|Integer|The user_id of the current user|Yes



## Get a card
This endpoint retrieves a user’s virtual card using it’s id.

#### Endpoint
```
{{BaseURL}}/user/user/get-card/{card_id}
```

#### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Yes
|user_id|Integer|The user_id of the current user|Yes
|card_id|Integer|The id attached to the virtual card.|Yes



## Remove card
This endpoint removes a user’s virtual card using it’s id.

#### Endpoint
```
{{BaseURL}}/user/user/remove-card/{card_id}
```

#### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Yes
|user_id|Integer|The user_id of the current user|Yes
|card_id|Integer|The id attached to the virtual card.|Yes


