# Donors

## Get All Donors


```shell
curl https://api.give.io/v1/users/2/donors
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
    "middle_initial": "",
    "last_name": "",
    "title": "",
    "company_name": "",
    "primary_email": "",
    "created_at": "",
    "donation_count": "",
    "donation_value": "",
    "additional_emails": [],
    "subscriptions": [],
    "donations": [],
    "addresses": []
  }
]
```

This endpoint retrieves all donors tied to an account.

### HTTP Request

`GET https://api.give.io/v1/users/<ID>/donors`


## Get a Specific Donor


```shell
curl https://api.give.io/v1/donors/2
  -H "Authorization: <API_KEY>"
```

```javascript
// javascript
```

> The above command returns JSON structured like this:

```json
{
  "ID": 8,
  "first_name": "Jake",
  "middle_initial": "E",
  "last_name": "Smith",
  "title": "Mr.",
  "email": "jakes@email.org",
  "created_at": "22018-07-30 13:28:32",
  "purchase_count": "0",
  "purchase_value": "0",
  "subscriptions": [],
  "donations": []
}
```

This endpoint retrieves a specific donor.

### HTTP Request

`GET https://api.give.io/v1/donors/<ID>`

## Create a Donor

Manually create a new Donor within Give.io. Data must be sent as JSON.
A donor object would also be created when a donation or subscription is
created.

```shell
$ curl https://api.give.io/v1/donors
  -X POST
  -d '{"first_name":"John", "last_name":"Doe", "email": "jdoe@email.com"}'
  -H "Content-Type: application/json"
  -H "Authorization: <API_KEY>"
```

```javascript
// Javscript
```

### HTTP Request

`POST https://api.give.io/v1/donors`

### Query Parameters

Parameter | Required | Description
--------- | ------- | -----------
email | YES | Valid Email Address
first_name  | YES | Donor's First Name
middle_initial | NO | Donor's Middle Initial
last_name | YES | Donor's Last Name
title | NO | Donor's preferred title (eg. Mr, Mrs, Dr, etc)


## Update a Donor

Update a donor's details. Data must be sent as JSON.
Data should be sent as a POST request, not a PUT request.
Only the fields that are passed are evaluated. To remove a
field, pass an empty string as the property value.

```shell
$ curl https://api.give.io/v1/donors/8
  -X POST
  -d '{"first_name":"Jake", "last_name":"Smith", "email": "jsmith@email.com"}'
  -H "Content-Type: application/json"
  -H "Authorization: <API_KEY>"
```

```javascript
// Javscript
```

### HTTP Request

`POST https://api.give.io/v1/donors/<ID>`

## Delete a Specific Donor

```shell
$ curl https://api.give.io/v1/donors/8
  -X DELETE
  -H "Authorization: <API_KEY>"
```

```javascript
// Javscript
```

> The above command returns the donor as it existed before deletion:

```json
{
  "ID": 8,
  "first_name": "Jake",
  "middle_initial": "E",
  "last_name": "Smith",
  "title": "Mr.",
  "email": "jakes@email.org",
  "created_at": "22018-07-30 13:28:32",
  "deleted_at": "2018-08-15 11:14:58",
  "purchase_count": "0",
  "purchase_value": "0",
  "subscriptions": [],
  "donations": []
}
```

This endpoint deletes a specific donor from the system entirely.
This call will return an error if the donor has any subscriptions
or donations that have not been removed first.

### HTTP Request

`DELETE https://api.give.io/v1/users/<ID>`

<aside class="warning">This action is immediate and irreversible.</aside>
