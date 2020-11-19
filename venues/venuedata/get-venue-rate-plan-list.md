# Get Venue Rate Plan List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getVenueRatePlanList" path="" %}
{% api-method-summary %}
Get Venue Rate Plan List
{% endapi-method-summary %}

{% api-method-description %}
Get the rate plan for a specific venue.
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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties. The venueId is required, for example {"venuId":10}

## Example Request

`Get a specific Venue’s Rate Plan List`

```javascript
{
  "venueId": 1
}
```

