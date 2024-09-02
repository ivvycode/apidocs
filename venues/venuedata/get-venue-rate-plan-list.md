# Get Venue Rate Plan List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getVenueRatePlanList" method="post" summary="Get Venue Rate Plan List" %}
{% swagger-description %}
Get the rate plan for a specific venue.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "meta": {
    "totalResults": 2,
    "start": 0,
    "perPage": null,
    "count": 2
  },
  "results": [
    {
      "id": 1,
      "name": "Basic Rate Plan",
      "code": "2-1",
      "description": "<p>Basic Room Pan</p> "
    },
    {
      "id": 2,
      "name": "Luxrious Plan",
      "code": "2-2",
      "description": "<p><strong>This is bit good:) here &#160;</strong></p> "
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties. The venueId is required, for example {"venuId":10}

## Example Request

`Get a specific Venue’s Rate Plan List`

```javascript
{
  "venueId": 1
}
```
