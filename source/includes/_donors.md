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
    "avatar": "",
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
  "ID": 1,
  "first_name": "",
  "middle_initial": "",
  "last_name": "",
  "title": "",
  "email": "",
  "avatar": "",
  "created_at": "",
  "purchase_count": "",
  "purchae_value": "",
  "subscriptions": [],
  "donations": []
}
```

This endpoint retrieves a specific donor.

### HTTP Request

`GET https://api.give.io/v1/donors/<ID>`

## Create a Donor

## Update a Donor

## Delete a Specific Donor
