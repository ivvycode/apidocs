# Get Venue Room Option List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getVenueRoomOptionList" path="" %}
{% api-method-summary %}
Get Venue Room Option List 
{% endapi-method-summary %}

{% api-method-description %}

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

```
{
  "meta": {
    "totalResults": 2,
    "start": 0,
    "perPage": 100,
    "count": 2
  },
  "results": [
    {
      "id": 1,
      "venueId": "1",
      "name": "Test Room Option 1",
      "description": "Test Room Option 1",
      "price": 100,
      "priceExcludedTaxIds": [1],
      "cost": 100,
      "costExcludedTaxIds": [1],
      "costCentreId": null,
      "modifiedDate": "2018-08-08 00:00:00 UTC"
    },
    {
      "id": 2,
      "venueId": "1",
      "name": "Test Room Option 2",
      "description": "Test Room Option 2",
      "price": 100,
      "priceExcludedTaxIds": [1],
      "cost": 100,
      "costExcludedTaxIds": [1],
      "costCentreId": null,
      "modifiedDate": "2018-08-08 00:00:00 UTC"
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the room options the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties. The venueId is required, for example {"venueId":10}

## Example Request

`Get a specific Venue’s Room Option List`

```javascript
{
  "venueId": 1
}
```

