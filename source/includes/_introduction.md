# Introduction

The Give.io REST API utilizes predictable, resource-oriented endpoints, and uses HTTP response codes to indicate API errors. We use built-in HTTP features, like HTTP authentication and HTTP verbs. JSON is returned by all API responses, including errors.

At this time, public registration for Developer Keys is not available.

## Requirements ##

To use the latest version of the REST API you must be:

* Using a valid API Key
* Accessing the API over HTTPS

> The base API is located here:

```none
https://api.give.io/v1/
```

## Errors ##

Occasionally you might encounter errors when accessing the API. There are four possible types:

* Invalid requests, such as using an unsupported HTTP method will result in `400 Bad Request`.
* Authentication or permission errors, such as incorrect API keys will result in `401 Unauthorized`.
* Requests to resources that don't exist or are missing required parameters will result in `404 Not Found`.
* Requests that cannot be processed due to a server error will result in `500 Internal Server Error`.

> `400 Bad Request` example:

```json
{
  "errors" : [
    {
      "code" : "giveio_api_unsupported_method",
      "message" : "Unsupported request method"
    }
  ]
}
```

> `401 Unauthorized` example:

```json
{
  "errors" : [
    {
      "code" : "giveio_api_authentication_error",
      "message" : "Consumer Key is invalid"
    }
  ]
}
```

> `404 Not Found` example:

```json
{
  "errors" : [
    {
      "code" : "giveio_api_invalid_order",
      "message" : "Invalid order"
    }
  ]
}
```

> `500 Internal Server Error` example:

```json
{
  "errors" : [
    {
      "code" : "giveio_api_invalid_handler",
      "message" : "The handler for the route is invalid"
    }
  ]
}
```

Errors return both an appropriate HTTP status code and response object which contains a `code` and `message` attribute. If an endpoint has any custom errors, they are documented within that endpoint.

## HTTP Verbs ##

The API uses the appropriate HTTP verb for each action:

|  Verb    |                               Description                               |
|----------|-------------------------------------------------------------------------|
| `HEAD`   | Can be used for any endpoint to return just the HTTP header information |
| `GET`    | Used for retrieving resources                                           |
| `PUT`    | Used for updating resources                                             |
| `POST`   | Used for creating resources                                             |
| `DELETE` | Used for deleting resources                                             |

## Tools ##
* [Postman](https://www.getpostman.com/) - A multi platform REST API GUI client (using Google Chrome or installing the app on Mac OS X or Windows).
* [CocoaRestClient](http://mmattozzi.github.io/cocoa-rest-client/) - A free, easy to use Mac OS X GUI client for interacting with the API, most useful when your test store has SSL enabled.
* [Paw HTTP Client](https://itunes.apple.com/us/app/paw-http-client/id584653203?mt=12) - Another excellent HTTP client for Mac OS X.
* [RESTClient, a debugger for RESTful web services](https://addons.mozilla.org/en-US/firefox/addon/restclient/) - Free Firefox add-on.
* [Advanced REST client](https://chrome.google.com/webstore/detail/advanced-rest-client/hgmloofddffdnphfgcellkdfbfbjeloo) - Free Google Chrome extension.