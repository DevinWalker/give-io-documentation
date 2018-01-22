# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://api.give.io/v1/authenticate"
  -H "Authorization: <API_KEY>"
```

```javascript
// Javascript Examples Coming Soon
```

> Make sure to replace `<API_KEY>` with your valid API key.

Give.io uses API keys to allow access to the API. During beta development, public access is not available.

Give.io expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: <API_KEY>`

<aside class="notice">
You must replace <code>&lt;API_KEY&gt;</code> with your personal API key.
</aside>
