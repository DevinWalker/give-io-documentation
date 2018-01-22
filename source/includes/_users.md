# Users

## Get All Users

```shell
curl "https://api.give.io/v1/users"
  -H "Authorization: <API_KEY>"
```

```javascript
// Javascript Examples Coming Soon
```

> The above request returns a collection of JSON objects structured like this:

```json
[
  {
    "ID": 1,
    "first_name": "",
    "last_name": "",
    "email": "",
    "avatar": "",
    "created_at": ""
  }
]
```

This endpoint retrieves all users.

### HTTP Request

`GET https://api.give.io/v1/users`


## Get a Specific User


```shell
curl "https://api.give.io/v1/users/2"
  -H "Authorization: <API_KEY>"
```

```javascript
// javascript
```

> The above command returns JSON structured like this:

```json
{
  "ID": 1,
  "first_name": "",
  "last_name": "",
  "email": "",
  "avatar": "",
  "created_at": ""
}
```

This endpoint retrieves a specific user.

### HTTP Request

`GET https://api.give.io/v1/users/<ID>`

## Create a New User

## Delete a Specific User

```shell
curl "https://api.give.io/v1/users/2"
  -X DELETE
  -H "Authorization: <API_KEY>"
```

```javascript
// Javscript
```

> The above command returns JSON structured like this:

```json
{
  "ID": 1,
  "first_name": "",
  "last_name": "",
  "email": "",
  "avatar": "",
  "created_at": "",
  "deleted_at": ""
}
```

This endpoint deletes a specific user.

### HTTP Request

`DELETE https://api.give.io/v1/users/<ID>`

<aside class="warning">This action is immediate and irreversible.</aside>
