# Get Venue Rate Plan List

### Description

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties. The venueId is required, for example {"venuId":10}

### API URL

`[PlatformAddress]/api/1.0/venue?action=getVenueRatePlanList`

### Example Request

`Get a specific Venue’s Rate Plan List`

```javascript
{
  "venueId": 1
}
```

### Example Response

```javascript
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

