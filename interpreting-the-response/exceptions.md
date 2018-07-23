# Exceptions

If an error occurred the response will be a [JSON](../development-reference/json-encoding.md) representation of what went wrong. This will provide the error code, a brief message as well as a specific code. The specific code is a useful piece of information to be provided in any bug reports.

Current exception codes and meanings are:

| Code | Description |
| --- | --- |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 405 | Method Not Allowed |
| 406 | Not Acceptable |
| 429 | Too Many Requests |
| 460 | Unknown |
| 461 | Failed Request |
| 462 | Session Expired |
| 463 | Key Revoked |
| 500 | Internal Server Error |
| 501 | Not Implemented |

Some exceptions will have an additional piece of information associated with the exception, which will contain more specific message about the exception.

**Exception: Specific Code 23016**

A parameter provided in the request did not validate correctly. For example, the API might have been expecting a number, but a string was provided instead. This exception gets thrown when the first invalid parameter is found.

The additional messages will contain the messages from the validator as to why the value was not validated.

**Example: Key does not validate error**

```javascript
Request (contact?action=getContact):
{
    "id":"wrong"
}
Response:
{
    "errorCode":400,
    "message":"'id' does not validate",
    "specificCode":23016,
    "additionalMessages":["Value must be a whole number"]
}
```

**Exception: Specific Code 23017**

A required parameter was missing from the request.

Example: Key is required error

```javascript
Request (contact?action=getContact):
{}
Response:
{
  "errorCode":400,
  "message":"'id' is required",
  "specificCode":23017
}
```

