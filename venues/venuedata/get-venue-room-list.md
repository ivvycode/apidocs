# Get Venue Room List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getVenueRoomList" path="" %}
{% api-method-summary %}
Get Venue Room List
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

```text
{
  "meta": {
    "totalResults": 1,
    "start": 0,
    "perPage": null,
    "count": 1
  },
  "results": [
    {
      "id": 1,
      "code": "2-1",
      "name": "Family RoomFamily",
      "description": "<p>The best family rooms:</p>  <ul><li>One double bed</li>  <li>Two child beds</li>  <li>Sitting area</li>  <li>Balcony</li> </ul>",
      "numStandardAdults": 2,
      "numExtraAdults": 1,
      "extraAdultCost": 100,
      "canSmoke": false,
      "capacity": 10,
      "marketplaceName": null
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties. The venueId is required, for example {"venuId":10}

## Example Request

`Get a specific Venue’s Room List`

```javascript
{
  "venueId": 1
}
```

