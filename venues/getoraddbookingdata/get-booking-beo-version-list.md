
## Get Booking BEO Version List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getBookingBeoVersionList" method="post" summary="Get Booking BEO Version List" %}
{% swagger-description %}
Retrieve a list of all versions of Banquet Event Orders (BEO) associated with a specific booking.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique ID of the venue to which the booking belongs.
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique ID of the booking whose BEO versions are to be retrieved.
{% endswagger-parameter %}

{% swagger-parameter name="onlyGenerated" type="boolean" in="body" required=false %}
Whether to fetch only generated documents.
{% endswagger-parameter %}

{% swagger-parameter name="beoNumber" type="integer" in="body" %}
The unique number assigned to the BEO whose versions are to be retrieved.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
    "meta": {
        "totalResults": 3,
        "start": 0,
        "perPage": 100,
        "count": 3
    },
    "results": [
        {
            "id": 1098,
            "venueId": 1,
            "bookingId": 25539,
            "beoType": 6,
            "beoNumber": 348,
            "version": 1,
            "versionNote": "",
            "file": {
                "url": "https://some.url/expiry2b",
                "urlExpiry": "2025-05-06 04:58:52 UTC",
                "filename": "29/12/2024 - BEO 348-1 - Test - Day1 - IPD-17309 Summarized tax.pdf"
            },
            "templateName": "Generic Venue Session BEO",
            "status": 4,
            "createdBy": 1,
            "createdDate": "2025-04-23 04:39:10 UTC"
        },
        {
            "id": 1099,
            "venueId": 1,
            "bookingId": 25539,
            "beoType": 6,
            "beoNumber": 348,
            "version": 2,
            "versionNote": "",
            "file": null,
            "templateName": "Generic Venue Session BEO",
            "status": 4,
            "createdBy": 1,
            "createdDate": "2025-04-23 04:39:35 UTC"
        },
        {
            "id": 1101,
            "venueId": 1,
            "bookingId": 25539,
            "beoType": 6,
            "beoNumber": 348,
            "version": 3,
            "versionNote": "Something 2",
            "file": {
                "url": "https://Some.url/expiry",
                "urlExpiry": "2025-05-06 04:58:52 UTC",
                "filename": "29/12/2024 - BEO 348-3 - Test - Day1 - IPD-17309 Summarized tax.pdf"
            },
            "templateName": "Generic Venue Session BEO",
            "status": 9,
            "createdBy": 1,
            "createdDate": "2025-04-23 04:39:58 UTC"
        }
    ]
}

```
{% endswagger-response %}
{% endswagger %}

## Example Request

```javascript
{
  "venueId": 1,
  "bookingId": 22363
  "beoNumber": 348
}
```

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of Banquet Event Orders (BEO) records that the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) properties.

## Booking BEO

| Property      | Type     | Description                                                                                       |
| ------------- | -------- | ------------------------------------------------------------------------------------------------- |
| id            | integer  | The unique ID of the BEO.                                                                          |
| venueId       | integer  | The unique ID of the venue associated with the BEO.                                                |
| bookingId     | integer  | The unique ID of the booking associated with the BEO.                                              |
| beoType       | integer  | The type of the BEO. See [BEO Type](get-booking-beo-list.md#beo-type)                             |
| beoNumber     | integer  | The unique number assigned to the BEO.                                                             |
| version       | integer  | The version of the BEO document.                                                                   |
| versionNote   | string   | Any notes regarding the BEO version.                                                              |
| file          | object   | The file details (can be `null` if no file exists). see [File](get-booking-beo-list.md#file)       |
| templateName  | string   | The name of the template used to generate the BEO.                                                 |
| status        | integer  | The status of the BEO. See [Status](get-booking-beo-list.md#status)                               |
| createdBy     | integer  | The user ID of the person who created the BEO.                                                     |
| createdDate   | datetime | The date and time when the BEO was created (UTC).                                                  |                                           |