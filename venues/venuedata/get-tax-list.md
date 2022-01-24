# Get Tax List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getTaxList" method="post" summary="Get Tax List" %}
{% swagger-description %}
Return the tax list for the venue.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
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
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Venues Tax List`

```javascript
{
  "venueId": 2
}
```

## Returns

`A collection object with the following properties in the results`

| Property      | Type    | Description                                                                            |
| ------------- | ------- | -------------------------------------------------------------------------------------- |
| id            | integer | The unique invoice identifier                                                          |
| name          | integer | The name of Tax                                                                        |
| type          | string  | The type of the tax. Whether Tax / Service Fee                                         |
| appliesTo     | integer | Whether the tax only applies to accommodation                                          |
| amountType    | integer | Tax or service fee amount / percent to apply on items. 1 = A percentage, 2 = An amount |
| amount        | double  | Percentage / Amount of the tax                                                         |
| taxIds        | array   | The taxes which are applied to the amount of the service fee                           |
| costcenterIds | array   | The cost centers to which the tax /service fee apply                                   |
