# Mailing Address
These endpoints allow you to manage mailing addresses for your users.

Please note that;
1. Each of the endpoint below is a `POST` request.
2. The endpoints needs the `api_key` and `user_id` as part of the request body.
3. `{address_id}` is sent as the last segment of the URL.
4. The `BaseURL` is the url that gives access to our APIs.


| Environment | Console URL | Base URLs |
| --- | --- | --- |
| Sandbox | https://sandbox.launch.new/login | https://api.deposits.dev/api/v2/ |
| Production | https://launch.new/client-admin/login | https://api.ondeposits.com/api/v2/ |


## Add an address
This endpoint creates a mailing address.

##### Endpoint
```
{{BaseURL}}/user/address/create
```

##### Parameters
|Parameters |Type |Description | |
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Required
|user_id|Integer|The user_id of the current user.|Required
|postal_code|String| |Required
|country|String| |Required
|state|String| |Required
|city|String| |Required
|address_1|String| |Required

##### Response
```
{
    "status": "success",
    "message": "address created",
    "data": {
        "user_id": 356,
        "postal_code": "34003",
        "country": "USA",
        "state": "Texas",
        "city": "Dallas",
        "address_1": "20 town avenue",
        "is_default": "false",
        "status": "active",
        "updated_at": "2022-02-23T17:26:00.000000Z",
        "created_at": "2022-02-23T17:26:00.000000Z",
        "id": 3
    }
}
```



## Update mailing address
This endpoint updates the details of a mailing address.

##### Endpoint
```
{{BaseURL}}/user/address/update/{address_id}
```

##### Parameters
|Parameters |Type |Description | |
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Required
|user_id|Integer|The user_id of the current user.|Required
|address_id|String|The identifier of the mailing address.|Required
|postal_code|String| |Required
|country|String| |Required
|state|String| |Required
|city|String| |Required
|address_1|String| |Required

##### Response
```
{
    "status": "success",
    "message": "address updated",
    "data": {
        "id": 3,
        "user_id": "356",
        "postal_code": "340030",
        "country": "USA",
        "state": "Texas",
        "city": "Dallas",
        "address_1": "20 town avenue town",
        "is_default": "false",
        "status": "active",
        "deleted_at": null,
        "created_at": "2022-02-23T17:26:00.000000Z",
        "updated_at": "2022-02-23T17:30:11.000000Z"
    }
}
```



## Get all mailing addresses
This endpoint returns all the mailing addresses owned by a user.

##### Endpoint
```
{{BaseURL}}/user/address/get
```

##### Parameters
|Parameters |Type |Description | |
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Required
|user_id|Integer|The user_id of the current user.|Required

##### Response
```
{
    "status": "success",
    "message": "addresses retrieved",
    "data": [
        {
            "id": 1,
            "user_id": "356",
            "postal_code": "500909",
            "country": "Nigeria",
            "state": "Lagos",
            "city": "Lagos",
            "address_1": "okene avenue",
            "is_default": "true",
            "status": "active",
            "deleted_at": null,
            "created_at": "2022-02-23T17:22:32.000000Z",
            "updated_at": "2022-02-23T17:22:32.000000Z"
        },
        {
            "id": 2,
            "user_id": "356",
            "postal_code": "34003",
            "country": "USA",
            "state": "Texas",
            "city": "Dallas",
            "address_1": "20 town avenue",
            "is_default": "false",
            "status": "active",
            "deleted_at": null,
            "created_at": "2022-02-23T17:23:22.000000Z",
            "updated_at": "2022-02-23T17:23:22.000000Z"
        }
    ]
}
```



## Get an address
This endpoint returns the details of the specified mailing address.

##### Endpoint
```
{{BaseURL}}/user/address/{address_id}
```

##### Parameters
|Parameters |Type |Description | |
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Required
|user_id|Integer|The user_id of the current user.|Required
|address_id|String|The identifier of the mailing address.|Required

##### Response
```
{
    "status": "success",
    "message": "address retrieved",
    "data": {
        "id": 2,
        "user_id": "356",
        "postal_code": "34003",
        "country": "USA",
        "state": "Texas",
        "city": "Dallas",
        "address_1": "20 town avenue",
        "is_default": "false",
        "status": "active",
        "deleted_at": null,
        "created_at": "2022-02-23T17:23:22.000000Z",
        "updated_at": "2022-02-23T17:23:22.000000Z"
    }
}
```



## Set default address
This endpoint sets the specified address as default.

##### Endpoint
```
{{BaseURL}}/user/address/set-default-address/{address_id}
```

##### Parameters
|Parameters |Type |Description | |
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Required
|user_id|Integer|The user_id of the current user.|Required
|address_id|String|The identifier of the mailing address.|Required

##### Response
```
{
    "status": "success",
    "message": "Default Address changed successfully",
    "data": {
        "id": 2,
        "user_id": "356",
        "postal_code": "34003",
        "country": "USA",
        "state": "Texas",
        "city": "Dallas",
        "address_1": "20 town avenue",
        "is_default": "true",
        "status": "active",
        "deleted_at": null,
        "created_at": "2022-02-23T17:23:22.000000Z",
        "updated_at": "2022-02-23T17:25:23.000000Z"
    }
}
```



## Get default address
This endpoint returns the default address of a user.

##### Endpoint
```
{{BaseURL}}/user/address/get-default-address
```

##### Parameters
|Parameters |Type |Description | |
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Required
|user_id|Integer|The user_id of the current user.|Required

##### Response
```
{
    "status": "success",
    "message": "Default Mailing Address Retrieved",
    "data": {
        "id": 4,
        "user_id": "372",
        "postal_code": "340030",
        "address_1": "20 town avenue town",
        "city": "Dallas",
        "state": "Texas",
        "country": "USA",
        "is_default": "true",
        "status": "active",
        "created_at": "2022-05-31T17:51:32.000000Z",
        "updated_at": "2022-06-01T10:12:12.000000Z"
    }
}
```



## Delete an address
This endpoint deletes the details of an address.

##### Endpoint
```
{{BaseURL}}/address/delete/{address_id}
```

##### Parameters
|Parameters |Type |Description | |
--- | --- | ---| ---|
|api_key|String|A unique identifier used to authorize access to your project.|Required
|user_id|Integer|The user_id of the current user.|Required
|address_id|String|The identifier of the mailing address.|Required

##### Response
```
{
    "status": "success",
    "message": "address deleted",
    "data": ""
}
```


