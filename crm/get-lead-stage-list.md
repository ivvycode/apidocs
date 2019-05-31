# Get Lead Stage List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=getLeadStageList" path="" %}
{% api-method-summary %}
Get Lead Stage List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of lead stages.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=false %}
The unique id of the venue to which the lead belongs
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
        "totalResults": 1,
        "start": 0,
        "perPage": 10,
        "count": 1
    },
    "results": [
        {
            "stageId": 1,
            "stageName": "Quoted"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the lead stages the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venue’s Lead Stage List`

```javascript
{
  "venueId": "1",
}
```
