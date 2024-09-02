# Get Venue Room List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getVenueRoomList" method="post" summary="Get Venue Room List" %}
{% swagger-description %}

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
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties. The venueId is required, for example {"venuId":10}

## Example Request

`Get a specific Venue’s Room List`

```javascript
{
  "venueId": 1
}
```
