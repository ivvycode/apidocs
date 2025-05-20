# Get Booking Document List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getBookingDocumentList" method="post" summary="Get Booking Document List" %}
{% swagger-description %}
Retrieve a list of documents associated with a specific booking.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique ID of the venue to which the booking belongs.
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique ID of the booking whose documents are to be retrieved.
{% endswagger-parameter %}

{% swagger-parameter name="onlyGenerated" type="boolean" in="body" required=false %}
Whether to fetch only generated documents.
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="body" %}
The starting index for pagination (zero-based).
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="body" %}
The number of documents to retrieve per page.
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
            "id": 3426,
            "venueId": 1,
            "bookingId": 22363,
            "type": 4,
            "file": {
                "url": "https://someurl/with/expiry",
                "urlExpiry": "2025-05-06 04:10:54 UTC",
                "filename": "25/12/2024 - Test - Peppers Soul Surfers Paradise Tax Exclusive - Accom Extra.pdf"
            },
            "templateName": "Accom Extra",
            "status": 4,
            "createdDate": "2025-04-09 02:34:21 UTC",
            "modifiedDate": "2025-04-09 02:38:36 UTC"
        },
        {
            "id": 3428,
            "venueId": 1,
            "bookingId": 22363,
            "type": 4,
            "file": {
                "url": "https://someurl/with/expiry2",
                "urlExpiry": "2025-05-06 04:10:54 UTC",
                "filename": "25/12/2024 - eashik - Peppers Soul Surfers Paradise Tax Exclusive - Accom Extra.pdf"
            },
            "templateName": "Accom Extra",
            "status": 4,
            "createdDate": "2025-04-09 02:50:39 UTC",
            "modifiedDate": "2025-04-09 02:57:45 UTC"
        },
        {
            "id": 3450,
            "venueId": 1,
            "bookingId": 22363,
            "type": 4,
            "file": null,
            "templateName": "Accom Extra",
            "status": 4,
            "createdDate": "2025-04-09 03:09:25 UTC",
            "modifiedDate": "2025-04-09 03:09:25 UTC"
        },
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

```javascript
{
  "venueId": 1,
  "bookingId": 3426,
  "onlyGenerated": true
}
```

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of booking room reservation records the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Booking Document

| Property     | Type     | Description                                                                               |
| ------------ | -------- | ----------------------------------------------------------------------------------------- |
| id           | integer  | The unique ID of the document.                                                            |
| venueId      | integer  | The unique ID of the venue associated with the document.                                  |
| bookingId    | integer  | The unique ID of the booking associated with the document.                                |
| type         | integer  | The type of document. See [Type](get-booking-document-list.md#type)       |
| templateName | string   | The name of the template used to generate the document.                                   |
| status       | integer  | The status of the document. See [Status](get-booking-document-list.md#status) |
| createdDate  | datetime | The date and time when the document was created (UTC).                                    |
| modifiedDate | datetime | The date and time when the document was last modified (UTC).                              |
| file         | object   | The file details (can be `null` if no file exists). see [File](get-booking-document-list.md#file)                                      |


## File

| Property      | Type                                                                          | Description                                                                                                                   |
| ------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
|  url          | string | The pre-signed URL where the document file can be accessed (if available).     |
|  urlExpiry    | datetime |  The expiry time of the pre-signed URL.     |
|  filename     | string | The display name of the file, typically including the template and context details.   |

## Type

| Type | Description                                       |
| --------- | ------------------------------------------------- |
| 1         | Quote created by the system                       |
| 2         | Contract created by the system                    |
| 3         | Quote uploaded by users                           |
| 4         | Contract uploaded by users                        |
| 5         | Other types of documents                          |
| 6         | Banquet Event Order (BEO) generated by the system |
| 7         | Resume                                            |
| 8         | Banquet Check                                     |

## Status

| Status | Description                                           |
| ----------- | ----------------------------------------------------- |
| 1           | Building (Document is in the building stage)          |
| 2           | Building Error (Error during document building)       |
| 3           | Draft (Document is still in draft form)               |
| 4           | Generated (Document's HTML is generated, PDF pending) |
| 5           | Sent (Document has been sent to the relevant party)   |
| 8           | Completed (Document has been completed)               |