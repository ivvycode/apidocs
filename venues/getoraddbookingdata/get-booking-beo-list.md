
## Get Booking BEO List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getBookingBeoList" method="post" summary="Get Booking BEO List" %}
{% swagger-description %}
Retrieve a list of Banquet Event Orders (BEO) associated with a specific booking.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique ID of the venue to which the booking belongs.
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique ID of the booking whose BEOs are to be retrieved.
{% endswagger-parameter %}

{% swagger-parameter name="onlyGenerated" type="boolean" in="body" required=false %}
Whether to fetch only generated documents.
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="body" %}
The starting index for pagination (zero-based).
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="body" %}
The number of BEOs to retrieve per page.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 100,
        "count": 1
    },
    "results": [
        {
            "id": 1114,
            "venueId": 1,
            "bookingId": 22363,
            "beoType": 3,
            "beoNumber": 360,
            "version": 1,
            "versionNote": "",
            "file": null,
            "templateName": "Generic Venue Booking BEO",
            "status": 4,
            "createdBy": 1,
            "createdDate": "2025-04-24 01:33:39 UTC"
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
| createdDate   | datetime | The date and time when the BEO was created (UTC).                                                  |

## File

| Property      | Type     | Description                                                                                       |
| ------------- | -------- | ------------------------------------------------------------------------------------------------- |
| url           | string   | The pre-signed URL where the BEO file can be accessed (if available).                             |
| urlExpiry     | datetime | The expiry time of the pre-signed URL.                                                            |
| filename      | string   | The display name of the file, typically including the template and context details.               |

## BEO Type

| Type | Description                                       |
| ---- | ------------------------------------------------- |
| 3    | Booking BEO                      |
| 6    | Session BEO                             |
| 11   | E-Booking BEO                              |
| 12   | E-Session BEO

## Status

| Status | Description                                           |
| ------ | ----------------------------------------------------- |
| 1      | Building (BEO document is in the building stage)      |
| 2      | Building Error (Error during BEO document building)   |
| 3      | Draft (BEO document is still in draft form)           |
| 4      | Generated (BEO's HTML is generated, PDF pending)      |
| 5      | Sent (BEO has been sent to the relevant party)        |
| 8      | Completed (BEO has been completed)                    |
| 9      | Finalised                                             |