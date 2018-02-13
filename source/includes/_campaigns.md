# Campaigns

## Get All Campaigns

```shell
curl https://api.give.io/v1/campaigns
  -H "give-client: <API_KEY>"
  -H "Authorization: Bearer <token>"
```

```javascript
// Javascript Examples Coming Soon
```

> The above request returns a collection of JSON objects structured like this:

```json
[
  {
    "ID": 1,
    "title": "",
    "created_at": "",
    "last_modified": "",
    "type": "standard",
    "start_at": "",
    "end_at": "",
    "has_end": true,
    "has_landing": false,
    "landing_url": "",
    "goal": {
      "enabled": true,
      "type": "amount",
      "value": "1000",
      "progress_color": "",
      "auto_close": true
    },

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

`GET https://api.give.io/v1/campaigns/`


## Get a Specific Campaign

`GET https://api.give.io/v1/campaigns/<ID>/`

This endpoint retrieves a specific campaign.

```shell
curl https://api.give.io/v1/campaigns/
  -H "give-client: <API_KEY>"
  -H "Authorization: Bearer <token>"
```

### HTTP Request

`GET https://api.give.io/v1/campaigns/ID/`

## Create a New Campaign

Create a new campaign within Give.io. Data must be sent as JSON.

```shell
curl https://api.give.io/v1/campaigns/
  -H "give-client: <API_KEY>"
  -H "Authorization: Bearer <token>"
```

### HTTP Request

`POST https://api.give.io/v1/campaigns/`

Parameter | Required | Description
--------- | -------- | -----------
title | Yes | "Campaign <ID>" | The title of the campaign.


## Update a Campaign

## Delete a Specific Campaign
