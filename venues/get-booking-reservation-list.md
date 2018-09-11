# Get Booking Reservation List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getBookingReservationList" path="" %}
{% api-method-summary %}
Get Booking Reservation List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of booking reservation for venue.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique identifier of the venue to which the bookings belong
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=false %}
The unique id of the booking to which the reservation belongs
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=false %}
The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\)
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=true %}
The number of booking reservations to fetch
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 5,
        "count": 1
    },
    "results": [{
        "bookingId": 4248,
        "venueId": 131,
        "reference": 164,
        "mainGuest": "Test1 Com1",
        "status": 2,
        "isFromGroup": false,
        "totalAmount": 200,
        "reservedRooms": [{
            "guestDetails": "Test1 Com1",
            "barId": 57,
            "roomId": 14,
            "groupId": null,
            "numRooms": 15,
            "arrivalDate": "2018-09-01",
            "departureDate": "2018-09-04",
            "totalAmount": 180,
            "taxes": [],
            "numAdults": 1,
            "numChildren": 0,
            "dayRates": [{
                "date": "2018-09-01",
                "barId": null,
                "cost": 180
            }, {
                "date": "2018-09-02",
                "barId": null,
                "cost": 190
            }, {
                "date": "2018-09-03",
                "barId": null,
                "cost": 175
            }]
        }, {
            "guestDetails": "Test2 Com2",
            "barId": 58,
            "roomId": 14,
            "groupId": null,
            "numRooms": 15,
            "arrivalDate": "2018-09-02",
            "departureDate": "2018-09-03",
            "totalAmount": 180,
            "taxes": [],
            "numAdults": 1,
            "numChildren": 0,
            "dayRates": [{
                "date": "2018-09-02",
                "barId": null,
                "cost": 200
            }, {
                "date": "2018-09-03",
                "barId": null,
                "cost": 210
            }]
        }]
    }]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the booking reservations the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## status:

One of the following values:

* 1 = Not Confirmed
* 2 = Confirmed
* 3 = Cancelled

