# Donations

## Get All Donations

```shell
curl https://api.give.io/v1/donations
  -H "Authorization: <API_KEY>"
```

```javascript
// Javascript Examples Coming Soon
```

> The above request returns a collection of JSON objects structured like this:


```json
[{
  "ID": 98,
  "campaign_ID": 67,
  "created_at": "2018-09-18 11:14:58",
  "customer": 8,
  "transaction_ID": "ch_1Bqa2P2eZvKYlo2CVaJa8DbC",
  "status": "succeeded",
  "amount": 100,
  "currency": "usd",
  "description": "",
  "metadata": { },
  "receipt_email": "jsmith@email.com"
}]
```

This endpoint retrieves all donations.

### HTTP Request

`GET https://api.give.io/v1/donations`

## Get All Donations by Donors

```shell
curl https://api.give.io/v1/donor/8/donations
  -H "Authorization: <API_KEY>"
```

```javascript
// Javascript Examples Coming Soon
```

> The above request returns a collection of JSON objects structured like this:


```json
[{
  "ID": 98,
  "campaign_ID": 67,
  "created_at": "2018-09-18 11:14:58",
  "customer": 8,
  "transaction_ID": "ch_1Bqa2P2eZvKYlo2CVaJa8DbC",
  "status": "succeeded",
  "amount": 100,
  "currency": "usd",
  "description": "",
  "metadata": { },
  "receipt_email": "jsmith@email.com"
}]
```

This endpoint retrieves all donations tied to a specific donor.

### HTTP Request

`GET https://api.give.io/v1/donors/<ID>/donations`

## Get All Donations by Campaign

```shell
curl https://api.give.io/v1/campaign/67/donations
  -H "Authorization: <API_KEY>"
```

```javascript
// Javascript Examples Coming Soon
```

> The above request returns a collection of JSON objects structured like this:


```json
[{
  "ID": 98,
  "campaign_ID": 67,
  "created_at": "2018-09-18 11:14:58",
  "customer": 8,
  "transaction_ID": "ch_1Bqa2P2eZvKYlo2CVaJa8DbC",
  "status": "succeeded",
  "amount": 100,
  "currency": "usd",
  "description": "",
  "metadata": { },
  "receipt_email": "jsmith@email.com"
}]
```

This endpoint retrieves all donations tied to a specific campaign.

### HTTP Request

`GET https://api.give.io/v1/campaigns/<ID>/donations`

## Get a Specific Donation

```shell
curl https://api.give.io/v1/donations/98
  -H "Authorization: <API_KEY>"
```

```javascript
// Javascript Examples Coming Soon
```

> The above request returns a JSON object structured like this:

```json
{
  "ID": 98,
  "campaign_ID": 67,
  "created_at": "2018-09-18 11:14:58",
  "customer": 8,
  "transaction_ID": "ch_1Bqa2P2eZvKYlo2CVaJa8DbC",
  "status": "succeeded",
  "amount": 100,
  "currency": "usd",
  "description": "",
  "metadata": { },
  "receipt_email": "jsmith@email.com"
}
```

This endpoint retrieves a specific donation transaction.

### HTTP Request

`GET https://api.give.io/v1/donations/<ID>`

## Create a Donation

This endpoint creates a new donation transaction.
If a donor ID is not supplied then a new donor will be created.

### HTTP Request

`POST https://api.give.io/v1/donations`

## Update a Donation

This endpoint updates a specific donation transaction.

### HTTP Request

`POST https://api.give.io/v1/donations/<ID>`

## Delete a Specific Donation

This endpoint deletes a specific donation transaction.

### HTTP Request

`DELETE https://api.give.io/v1/donations/<ID>`

<aside class="warning">This action is immediate and irreversible.</aside>
