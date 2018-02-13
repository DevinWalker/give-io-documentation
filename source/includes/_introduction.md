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

## Response Structure ##

Give.io sends its API responses in a response wrapper along with additional information, such as whether or not the request was successful, any error messages if it was not, or pagination links for large collections. If the endpoint you requested returns any data, it will be in the response object's `data` property.


> Response Object example:

```json
{
  "data" : [
    {...},
    {...}
  ],
  "success" : "true",
  "links": {
    "first": "https://api.give.io/v1/donors?page=1",
    "last": "https://api.give.io/v1/donors?page=1",
    "prev": null,
    "next": null
  },
  "meta": {
    "current_page": 1,
    "from": 1,
    "last_page": 1,
    "path": "https://api.give.io/v1/donors",
    "per_page": 15,
    "to": 10,
    "total": 10
  }
}
```

## Errors ##

Occasionally you might encounter errors when accessing the API. There are four possible types:

Error Code | Meaning
---------- | -------
400 | Bad Request -- Invalid requests, such as using an unsupported HTTP method will result in `400 Bad Request`.
401 | Unauthorized -- Authentication or permission errors, such as incorrect API keys will result in `401 Unauthorized`.
403 | Forbidden -- The request is hidden for administrators only.
404 | Not Found -- Requests to resources that don't exist or are missing required parameters will result in `404 Not Found`.
429 | Too Many Requests -- Request too large. Slow down!
500 | Internal Server Error -- Requests that cannot be processed due to a server error will result in `500 Internal Server Error`.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.


> `400 Bad Request` example:

```json
{
  "data" :     {
    "code" : "giveio_api_unsupported_method",
    "message" : "Unsupported request method"
  },
  "success" : "false"
}
```

> `401 Unauthorized` example:

```json
{
  "data" :     {
    "code" : "giveio_api_authentication_error",
    "message" : "Consumer Key is invalid"
  },
  "success" : "false"
}
```

> `404 Not Found` example:

```json
{
  "data" :     {
    "code" : "giveio_api_invalid_order",
    "message" : "Invalid order"
  },
  "success" : "false"
}
```

> `500 Internal Server Error` example:

```json
{
  "data" :     {
    "code" : "giveio_api_invalid_handler",
    "message" : "The handler for the route is invalid"
  },
  "success" : "false"
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
