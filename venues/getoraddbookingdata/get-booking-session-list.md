# Get Booking List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getBookingSessionList" path="" %}
{% api-method-summary %}
Get Booking Session List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of booking sessions.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=false %}
The id of the booking
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=true %}
The number of bookings to get in a single call
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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venue’s Booking Session List`

```javascript
{
  "venueId": "1",
  "perPage": 1
}
```