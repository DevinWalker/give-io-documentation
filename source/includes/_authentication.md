# Authentication

## Client API Key

> To make a successful request with both a client API Key and an Authenticated JWT, use this code:

```shell
# With shell, you can just pass the correct headers with each request
curl https://api.give.io/v1/<endpoint>
  -H "give-client: <API_KEY>"
  -H "Authorization: Bearer <token>"
```

```javascript
// Javascript Examples Coming Soon
```

> Make sure to replace `<API_KEY>` with your valid API key.

Give.io uses API Client keys to allow access to the API, and JSON Web Tokens for individual user authentication. **During beta development, public access is not available**.

Give.io expects the API Client key to be included in *all* API requests to the server in a header that looks like the following:

`give-client: <API_KEY>`

<aside class="notice">
You must replace <code>&lt;API_KEY&gt;</code> with your personal API key.
</aside>


## User authentication

JSON Web Token (JWT) is an open standard ([RFC 7519](https://tools.ietf.org/html/rfc7519)) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed by the originating server.

Give.io uses these tokens for user authentication within the application. You will need to pass this token with each request as a typical Authentication header. You can request this initial token from the authentication endpoint with an Authorization header that contains the word `Basic` word followed by a space and a base64-encoded string `username:password`.

> To request an Authenticated JWT, use this code:

```shell
curl https://api.give.io/v1/authenticate/token
  -H "give-client: <API_KEY>"
  -H "Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ="
```

<aside class="notice">
You must replace <code>dXNlcm5hbWU6cGFzc3dvcmQ=</code> with your own encoded username and password.
</aside>


> The above request returns a basic JSON response object containing your new token:

```json
{
    "success": true,
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOjQsImlzcyI6Imh0dHA6Ly9sb2NhbGhvc3Q6ODg4OC9tZXNhbi1sYXJhdmVsLWp3dC1hdXRoZW50aWNhdGlvbjIvcHVibGljL2FwaS9sb2dpbiIsImlhdCI6MTUwMjU2NzE5MSwiZXhwIjoxNTAyNTcwNzkxLCJuYmYiOjE1MDI1NjcxOTEsImp0aSI6IkVIVWV6dVp0UDhhSmQ2QUUifQ.OjlzNKmTItphLs29B7WsFstmrtgDW2qE7gv26LcR3Og"
    }
}```
