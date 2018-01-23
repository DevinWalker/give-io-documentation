# Campaigns

## Get All Campaigns

```shell
curl https://api.give.io/v1/users/2/campaigns
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
    "created_at": "",
    "type": "standard",
    "start_at": "",
    "end_at": "",
    "has_end": true,
    "has_landing": false,
    "landing_url": "",
    "goal": {
      "enabled": true,
      "type": "amount",
      "value": "1000.000000"
    },
    "progress_color": "",
    "autoclose": true,
    "terms": {
      "enabled": true,
      "label": "Terms & Conditions",
      "content": ""
    }
  }
]
```

This endpoint retrieves all users.

### HTTP Request

`GET https://api.give.io/v1/users/<ID>/campaigns`

## Get a Specific Campaign

## Create a Campaign

## Update a Campaign

## Delete a Specific Campaign
