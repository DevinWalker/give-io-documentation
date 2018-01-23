# Users

### User Object
Property | Description
--------- | -------
ID | Unique ID
first_name | First Name
last_name | Last Name
email | Valid Contact Email
organizations | A collection of organizations that this user belongs to
avatar | URL to User's Avatar image
created_at | ISO8601 Timestamp of Account Creation
updated_at | ISO8601 Timestamp of the last account update
last_login | ISO8601 Timestamp of the last valid login

### Roles

Role | Permissions
--------- | -------
Owner | TBD
Administrator | TBD
Manager | TBD
Developer | TBD
Analyst | TBD
Support | TBD

## Get All Users

```shell
$ curl https://api.give.io/v1/users
  -H "Authorization: <API_KEY>"
```

```javascript
// Javascript Examples Coming Soon
```

> The above request returns a collection of JSON objects structured like this:

```json
[
  {
    "ID": 862,
    "first_name": "John",
    "last_name": "Doe",
    "email": "jdoe@email.com",
    "organizations": [
      {
        "ID": 234,
        "name": "",
        "role": "owner"
      }
    ],
    "avatar": "https://avatars.give.io/862/240.jpg",
    "created_at": "2018-07-30 13:28:32",
    "last_login": "2018-08-12 08:04:00"
  }
]
```

This endpoint retrieves all users as a paginated collection.

### HTTP Request

`GET https://api.give.io/v1/users`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
limit  | 25 | Limit number of results returned per page.
page | 1 | Used along with limit to determine offset.


## Get Users From Organization

```shell
$ curl https://api.give.io/v1/organization/234/users
  -H "Authorization: <API_KEY>"
```

```javascript
// Javascript Examples Coming Soon
```

> The above request returns a collection of JSON objects structured like this:

```json
[
  {
    "ID": 862,
    "first_name": "John",
    "last_name": "Doe",
    "email": "jdoe@email.com",
    "organizations": [
      {
        "ID": 234,
        "name": "",
        "role": "owner"
      }
    ],
    "avatar": "https://avatars.give.io/862/240.jpg",
    "created_at": "2018-07-30 13:28:32",
    "last_login": "2018-08-12 08:04:00"
  }
]
```

This endpoint retrieves all users belonging to a given organization as a paginated collection.

### HTTP Request

`GET https://api.give.io/v1/organization/<ID>/users`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
limit  | 25 | Limit number of results returned per page.
page | 1 | Used along with limit to determine offset.

## Get a Specific User


```shell
$ curl https://api.give.io/v1/users/2
  -H "Authorization: <API_KEY>"
```

```javascript
// javascript
```

> The above command returns JSON structured like this:

```json
{
  "ID": 862,
  "first_name": "John",
  "last_name": "Doe",
  "email": "jdoe@email.com",
  "organizations": [
    {
      "ID": 234,
      "name": "",
      "role": "owner"
    }
  ],
  "avatar": "https://avatars.give.io/862/240.jpg",
  "created_at": "2018-07-30 13:28:32",
  "last_login": "2018-08-12 08:04:00"
}
```

This endpoint retrieves a specific user.

### HTTP Request

`GET https://api.give.io/v1/users/<ID>`

## Create a New User

Create a new user within Give.io. Data must be sent as JSON.

```shell
# As a data string
$ curl https://api.give.io/v1/users
  -X POST
  -d '{"first_name":"John", "last_name":"Doe", "email": "jdoe@email.com", "password": "ABC123"}'
  -H "Content-Type: application/json"
  -H "Authorization: <API_KEY>"

# From a file
$ curl https://api.give.io/v1/users
  -X POST
  -d "@data.json"
  -H "Content-Type: application/json"
  -H "Authorization: <API_KEY>"
```

```javascript
// Javscript
```

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
email | YES | Valid Email Address
password | YES | User's initial password
first_name  | YES | User's First Name
last_name | NO | User's Last Name
organization | NO | ID of initial organization
role | NO | Initial Permissions Role, ignored if organization is not set

## Delete a Specific User

```shell
$ curl https://api.give.io/v1/users/2
  -X DELETE
  -H "Authorization: <API_KEY>"
```

```javascript
// Javscript
```

> The above command returns the user as it existed before deletion:

```json
{
  "ID": 862,
  "first_name": "John",
  "last_name": "Doe",
  "email": "jdoe@email.com",
  "organizations": [
    {
      "ID": 234,
      "name": "",
      "role": "owner"
    }
  ],
  "avatar": "https://avatars.give.io/862/240.jpg",
  "created_at": "2018-07-30 13:28:32",
  "last_login": "2018-08-12 08:04:00",
  "deleted_at": "2018-08-15 11:14:58"
}
```

This endpoint deletes a specific user from the system entirely. The user will be removed from any organizations they belong.
This call will return an error if the user has an Owner role in any organization that has not been removed first.

### HTTP Request

`DELETE https://api.give.io/v1/users/<ID>`

<aside class="warning">This action is immediate and irreversible.</aside>
