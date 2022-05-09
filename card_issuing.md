# Card Issuing

These endpoints allow you to create and manage cards.

Please note that;
1. Each of the endpoint below is a `POST` request.
2. The endpoints needs the `api_key` and `user_id` as part of the request body.
3. `{card_id}` is sent as the last segment of the URL.
4. For the purpose of this test lets use the sandbox URL.
5. The `BaseURL` is the url that gives access to our APIs.

| Environment | Console URL | Base URLs |
| --- | --- | --- |
| Sandbox | https://console.deposits.dev/client-admin/login | https://staging.api.deposits.com/api/v1/ |
| Production | https://console.deposits.com/client-admin/login | https://api.deposits.com/api/v1/ |


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

#### Response
``` 
{
    "status": "success",
    "message": "Card created successfully",
    "data": {
        "user_id": 963,
        "card_issuer": "privacy",
        "card_token": "1b87a9e0-f141-4587-9361-ee82bb93d615",
        "card_obj": "{\"created\":\"2022-01-27T11:11:01Z\",\"token\":\"1b87a9e0-f141-4587-9361-ee82bb93d615\",\"last_four\":\"4617\",\"hostname\":\"\",\"memo\":\"Swys Demo card\",\"type\":\"UNLOCKED\",\"spend_limit\":0,\"spend_limit_duration\":\"TRANSACTION\",\"state\":\"OPEN\",\"funding\":{\"created\":\"2021-05-13 13:49:27\",\"token\":\"6d07a118-e515-422d-9bbf-361cfda44489\",\"type\":\"DEPOSITORY_CHECKING\",\"state\":\"ENABLED\",\"nickname\":\"\",\"account_name\":\"Lina swe\",\"last_four\":\"4454\"},\"auth_rule_tokens\":[],\"pan\":\"4111111242574617\",\"cvv\":\"324\",\"exp_month\":\"01\",\"exp_year\":\"2028\"}",
        "status": "active",
        "updated_at": "2022-01-27T11:11:01.000000Z",
        "created_at": "2022-01-27T11:11:01.000000Z",
        "id": 166,
        "card_obj_json": {
            "created": "2022-01-27T11:11:01Z",
            "token": "1b87a9e0-f141-4587-9361-ee82bb93d615",
            "last_four": "4617",
            "hostname": "",
            "memo": "Swys Demo card",
            "type": "UNLOCKED",
            "spend_limit": 0,
            "spend_limit_duration": "TRANSACTION",
            "state": "OPEN",
            "funding": {
                "created": "2021-05-13 13:49:27",
                "token": "6d07a118-e515-422d-9bbf-361cfda44489",
                "type": "DEPOSITORY_CHECKING",
                "state": "ENABLED",
                "nickname": "",
                "account_name": "Lina swe",
                "last_four": "4454"
            },
            "auth_rule_tokens": [],
            "pan": "4111111242574617",
            "cvv": "324",
            "exp_month": "01",
            "exp_year": "2028"
        }
    }
}
```


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

#### Response
```
{
    "status": "success",
    "message": "User cards",
    "data": [
        {
            "id": 3,
            "user_id": "3",
            "card_issuer": "privacy",
            "card_token": "b2603dcd-f565-44e4-8600-171708c4a340",
            "card_obj": "{\"created\":\"2021-04-29T16:03:31Z\",\"cvv\":\"684\",\"exp_month\":\"04\",\"exp_year\":\"2027\",\"funding\":{\"account_name\":\"Lina swe\",\"bankAccountID\":\"2266\",\"created\":\"2021-04-25 03:01:22\",\"last_four\":\"4454\",\"nickname\":\"\",\"state\":\"ENABLED\",\"token\":\"03eac644-1ab2-478b-b85b-51ee427cce78\",\"type\":\"DEPOSITORY_CHECKING\"},\"hostname\":\"\",\"last_four\":\"1052\",\"memo\":\"Swys Demo card\",\"pan\":\"4111111232401052\",\"spend_limit\":0,\"spend_limit_duration\":\"TRANSACTION\",\"state\":\"OPEN\",\"token\":\"b2603dcd-f565-44e4-8600-171708c4a340\",\"type\":\"UNLOCKED\"}",
            "status": "active",
            "created_at": "2021-04-29T16:03:31.000000Z",
            "updated_at": "2021-04-29T16:03:31.000000Z",
            "card_obj_json": {
                "created": "2021-04-29T16:03:31Z",
                "cvv": "684",
                "exp_month": "04",
                "exp_year": "2027",
                "funding": {
                    "account_name": "Lina swe",
                    "bankAccountID": "2266",
                    "created": "2021-04-25 03:01:22",
                    "last_four": "4454",
                    "nickname": "",
                    "state": "ENABLED",
                    "token": "03eac644-1ab2-478b-b85b-51ee427cce78",
                    "type": "DEPOSITORY_CHECKING"
                },
                "hostname": "",
                "last_four": "1052",
                "memo": "Swys Demo card",
                "pan": "4111111232401052",
                "spend_limit": 0,
                "spend_limit_duration": "TRANSACTION",
                "state": "OPEN",
                "token": "b2603dcd-f565-44e4-8600-171708c4a340",
                "type": "UNLOCKED"
            }
    ]
}
```


## Get a card
This endpoint retrieves a user’s virtual card using it’s id.

#### Endpoint
```
{{BaseURL}}/user/get-card/{card_id}
```

#### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Yes
|user_id|Integer|The user_id of the current user|Yes
|card_id|Integer|The id attached to the virtual card.|Yes

#### Response
```
{
    "status": "success",
    "message": "User card",
    "data": [
        {
            "id": 4,
            "user_id": "3",
            "card_issuer": "privacy",
            "card_token": "b2603dcd-f565-44e4-8600-171708c4a340",
            "card_obj": "{\"created\":\"2021-04-29T16:03:31Z\",\"cvv\":\"684\",\"exp_month\":\"04\",\"exp_year\":\"2027\",\"funding\":{\"account_name\":\"Lina swe\",\"bankAccountID\":\"2266\",\"created\":\"2021-04-25 03:01:22\",\"last_four\":\"4454\",\"nickname\":\"\",\"state\":\"ENABLED\",\"token\":\"03eac644-1ab2-478b-b85b-51ee427cce78\",\"type\":\"DEPOSITORY_CHECKING\"},\"hostname\":\"\",\"last_four\":\"1052\",\"memo\":\"Swys Demo card\",\"pan\":\"4111111232401052\",\"spend_limit\":0,\"spend_limit_duration\":\"TRANSACTION\",\"state\":\"OPEN\",\"token\":\"b2603dcd-f565-44e4-8600-171708c4a340\",\"type\":\"UNLOCKED\"}",
            "status": "active",
            "created_at": "2021-04-29T16:03:31.000000Z",
            "updated_at": "2021-04-29T16:03:31.000000Z",
            "card_obj_json": {
                "created": "2021-04-29T16:03:31Z",
                "cvv": "684",
                "exp_month": "04",
                "exp_year": "2027",
                "funding": {
                    "account_name": "Lina swe",
                    "bankAccountID": "2266",
                    "created": "2021-04-25 03:01:22",
                    "last_four": "4454",
                    "nickname": "",
                    "state": "ENABLED",
                    "token": "03eac644-1ab2-478b-b85b-51ee427cce78",
                    "type": "DEPOSITORY_CHECKING"
                },
                "hostname": "",
                "last_four": "1052",
                "memo": "Swys Demo card",
                "pan": "4111111232401052",
                "spend_limit": 0,
                "spend_limit_duration": "TRANSACTION",
                "state": "OPEN",
                "token": "b2603dcd-f565-44e4-8600-171708c4a340",
                "type": "UNLOCKED"
            }
    ]
}
```


## Remove card
This endpoint removes a user’s virtual card using it’s id.

#### Endpoint
```
{{BaseURL}}/user/remove-card/{card_id}
```

#### Parameters
|Parameters |Type |Description |Required
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Yes
|user_id|Integer|The user_id of the current user|Yes
|card_id|Integer|The id attached to the virtual card.|Yes

#### Response
```
{
    "status": "success",
    "message": "User card removed",
    "data": {
        "id": 8,
        "user_id": "343",
        "business_id": null,
        "card_issuer": "privacy",
        "card_token": "f140efd1-995b-4faf-a233-dc1248ade419",
        "card_obj": "{\"created\":\"2021-08-03T06:37:29Z\",\"cvv\":\"374\",\"exp_month\":\"08\",\"exp_year\":\"2027\",\"funding\":{\"account_name\":\"Lina swe\",\"created\":\"2021-05-13 13:49:27\",\"last_four\":\"4454\",\"nickname\":\"\",\"state\":\"ENABLED\",\"token\":\"6d07a118-e515-422d-9bbf-361cfda44489\",\"type\":\"DEPOSITORY_CHECKING\"},\"hostname\":\"\",\"last_four\":\"9334\",\"memo\":\"Swys Demo card\",\"pan\":\"4111111293809334\",\"spend_limit\":0,\"spend_limit_duration\":\"TRANSACTION\",\"state\":\"OPEN\",\"token\":\"f140efd1-995b-4faf-a233-dc1248ade419\",\"type\":\"UNLOCKED\"}",
        "status": "deactive",
        "created_at": "2021-08-03T06:37:29.000000Z",
        "updated_at": "2021-08-05T15:25:42.000000Z",
        "card_obj_json": {
            "created": "2021-08-03T06:37:29Z",
            "cvv": "374",
            "exp_month": "08",
            "exp_year": "2027",
            "funding": {
                "account_name": "Lina swe",
                "created": "2021-05-13 13:49:27",
                "last_four": "4454",
                "nickname": "",
                "state": "ENABLED",
                "token": "6d07a118-e515-422d-9bbf-361cfda44489",
                "type": "DEPOSITORY_CHECKING"
            },
            "hostname": "",
            "last_four": "9334",
            "memo": "Swys Demo card",
            "pan": "4111111293809334",
            "spend_limit": 0,
            "spend_limit_duration": "TRANSACTION",
            "state": "OPEN",
            "token": "f140efd1-995b-4faf-a233-dc1248ade419",
            "type": "UNLOCKED"
        }
    }
}
```


