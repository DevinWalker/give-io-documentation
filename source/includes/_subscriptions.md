# Subscriptions

## Get All Subscriptions

```shell
curl https://api.give.io/v1/subscriptions?filter=user&ID=2
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
    "donor": 2,
    "frequency": "",
    "donation_count": "",
    "initial_amount": "",
    "recurring_amount": "",
    "subscription_changes": [],
    "status": "",
    "notes": [],
    "expiration_date": "",
    "created_at": "",
    "updated_at": ""
  }
]
```

This endpoint retrieves all subscriptions tied to a donor, user, organization, chapter or campaign.

### HTTP Request

`GET https://api.give.io/v1/subscriptions`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
filter  | NULL | How to refine the results returned. Possible values: 'donor', 'user', 'organization', or 'chapter'
ID | 0 | The ID of the filter object used to limit results.

## Get a Specific Subscription

## Create a Subscription

## Update a Subscription

## Delete a Specific Subscription
