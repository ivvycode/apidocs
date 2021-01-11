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

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique invoice identifier |
| name | integer | The name of Tax |
| type | string | The type of the tax. Whether Tax / Service Fee |
| appliesTo | integer | Whether the tax only applies to accommodation |
| amountType | integer | Tax or service fee amount / percent to apply on items. 1 = A percentage, 2 = An amount |
| amount | double | Percentage / Amount of the tax |
| taxIds | array | The taxes which are applied to the amount of the service fee |
| costcenterIds | array | The cost centers to which the tax /service fee apply |

