# Get Tax List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getTaxList" path="" %}
{% api-method-summary %}
Get Tax List
{% endapi-method-summary %}

{% api-method-description %}
Return the tax list for the venue.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
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
    "perPage": 1,
    "count": 1
  },
  "results": [
    {
      "id": 2,
      "name": "GST"
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get Venues Tax List`

```javascript
{
  "venueId": 2
}
```

## Returns

`A collection object with the following properties in the results`

| Property | Description |
| :--- | :--- |
| id | The unique invoice identifier |
| name | The name of Tax |

