# Get Venue Room List

### Description

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties. The venueId is required, for example {"venuId":10}

### API URL

`[PlatformAddress]/api/1.0/venue?action=getVenueRoomList`

### Example Request

`Get a specific Venue’s Room List`

```javascript
{
  "venueId": 1
}
```

### Example Response

```javascript
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

