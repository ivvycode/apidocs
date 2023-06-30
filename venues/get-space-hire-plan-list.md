# Get Space Hire Plans

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getSpaceHirePlanList" path="" %}
{% api-method-summary %}
Get Space Hire Plan List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of space hire plans.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=false %}
The number of space hire plan to get in a single call
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 50,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "name": "RHP",
            "code": "RHP",
            "description": null,
            "createdDate": "2017-12-18 12:17:49 UTC",
            "modifiedDate": "2018-01-15 05:44:41 UTC"
        },
        {
            "id": 8,
            "name": "Test Hire Plan",
            "code": "HIRE123",
            "description": "<p>test</p> ",
            "createdDate": "2019-04-03 11:27:42 UTC",
            "modifiedDate": "2020-04-29 04:43:02 UTC"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the space hire plans the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific space hire plan list`

```javascript
{
  "venueId": "1",
  "perPage": "50",
}
```