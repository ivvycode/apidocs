# Get Booking Session List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getBookingSessionList" method="post" summary="Get Booking Session List" %}
{% swagger-description %}
Get a list of booking sessions.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="path" %}
The id of the booking
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of bookings to get in a single call
{% endswagger-parameter %}

{% swagger-parameter name="orderBy" type="string" in="request" %}
Order the reponse by column
{% endswagger-parameter %}

{% swagger-parameter name="orderDir" type="string" in="spec" %}
asc|desc
{% endswagger-parameter %}
{% endswagger %}

```
{
    "meta": {
        "totalResults": 1550,
        "start": 0,
        "perPage": 1,
        "count": 1
    },
    "results": [
        {
            "id": 5260,
            "bookingId": 10960,
            "name": "abc",
            "startDate": "2020-04-14",
            "endDate": "2020-04-14",
            "startTime": "08:00:00",
            "endTime": "10:30:00",
            "spaceVenueId": 1,
            "spaceId": 3,
            "spaceLayout": 3,
            "customLayoutName": null,
            "tariffId": 1,
            "cost": 12,
            "costAfterAdjustment": 12,
            "costDiscount": 0,
            "costSurcharge": null,
            "amount": 13.2,
            "totalDiscount": 0,
            "totalSurcharge": null,
            "totalTaxAmount": 1.2,
            "excludedTaxIds": [],
            "sfExcludedTaxIds": [],
            "setupTime": null,
            "setdownTime": null,
            "canBeMoved": 1,
            "minAttendeesGuaranteed": 10,
            "agreedAttendees": 10,
            "expectedAttendees": 10,
            "guaranteedAttendees": 10,
            "setAttendees": 10,
            "actualAttendees": 10,
            "signage": "",
            "isSignageVisible": 1,
            "createdDate": "2020-02-24 01:13:39 UTC",
            "modifiedDate": "2020-02-24 01:16:43 UTC",
            "roomHireType": 1,
            "includeInPackage": false,
            "bookingPackageId": 0,
            "costcenterId": 4,
            "overridePax": 1,
            "sessionTypeId": 0,
            "beoNumbers": null
        }
    ]
}
```

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venue’s Booking Session List`

```javascript
{
  "venueId": "1",
  "perPage": 1
}
```
