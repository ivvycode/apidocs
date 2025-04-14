# Get Rate Plan Room Rate List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getRoomRateList" method="post" summary="Get Rate Plan Room Rate List" %}
{% swagger-description %}
Get a list of rate plan room rates.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" required=true in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="barId" type="integer" required=true in="path" %}
The id of the rate plan
{% endswagger-parameter %}

{% swagger-parameter name="barRateId" type="integer" required=true in="path" %}
The id of the rate plan rate
{% endswagger-parameter %}

{% swagger-parameter name="roomId" type="integer" required=false in="path" %}
The id of the room
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 3,
        "start": 0,
        "perPage": 3,
        "count": 3
    },
    "results": [
        {
            "id": 1,
            "barId": 1,
            "barRateId": 1,
            "roomId": 1,
            "cost": 55,
            "costDouble": null,
            "costTriple": null,
            "costQuad": null,
            "costExcludedTaxIds": [],
            "actualCost": 45,
            "actualCostDouble": null,
            "actualCostTriple": null,
            "actualCostQuad": null,
            "actualCostExcludedTaxIds": []
        },
        {
            "id": 2,
            "barId": 1,
            "barRateId": 1,
            "roomId": 22,
            "cost": 50,
            "costDouble": null,
            "costTriple": null,
            "costQuad": null,
            "costExcludedTaxIds": [],
            "actualCost": 45,
            "actualCostDouble": null,
            "actualCostTriple": null,
            "actualCostQuad": null,
            "actualCostExcludedTaxIds": []
        },
        {
            "id": 3,
            "barId": 1,
            "barRateId": 1,
            "roomId": 23,
            "cost": 50,
            "costDouble": 70,
            "costTriple": 0,
            "costQuad": 0,
            "costExcludedTaxIds": [],
            "actualCost": 0,
            "actualCostDouble": 0,
            "actualCostTriple": 0,
            "actualCostQuad": 0,
            "actualCostExcludedTaxIds": []
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the room rates the user has access to.  it does not accept [pagination](../../getting-started/interpreting-the-response/pagination.md) or [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

```javascript
{
  "venueId": 1,
  "barId": 1,
  "barRateId": 1,
}
```

## Rate Plan Room Rate

| Property              | Type                                                                       | Description                                                                       |
| --------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| id                    | integer                                                                    | The unique id of the room rate                                                         |
| barId                 | integer                                                                    | The unique id of the rate plan                                                    |
| barRateId             | integer                                                                    | The unique id of the rate plan rate                                               |
| roomId                | integer                                                                    | The unique id of the room                                               |
| cost                  | double                                                                     | The sale price of the room rate. Represents single occupancy when multi occupancy is enabled.                                               |
| costDouble            | double                                                                     | The sale price of the room rate for double occupancy                              |
| costTriple            | double                                                                     | The sale price of the room rate for triple occupancy                              |
| costQuad              | double                                                                     | The sale price of the room rate for quad occupancy                              |
| costExcludedTaxIds    | array                                                                      | The excluded tax identifiers of the sale price                           |
| actualCost            | double                                                                     | The cost of the room rate. Represents single occupancy when multi occupancy is enabled.                                               |
| actualCostDouble      | double                                                                     | The cost of the room rate for double occupancy                              |
| actualCostTriple      | double                                                                     | The cost of the room rate for triple occupancy                              |
| actualCostQuad        | double                                                                     | The cost of the room rate for quad occupancy                              |
| actualCostExcludedTaxIds    | array                                                                      | The excluded tax identifiers of the cost                           |