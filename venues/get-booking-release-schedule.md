# Get Booking Release Schedule

{% api-method method="post" host="\[PlatformAddress\]/api/1.0" path="/venue?action=getBookingReleaseSchedule" %}
{% api-method-summary %}
Get Booking Release Schedule
{% endapi-method-summary %}

{% api-method-description %}
Get a list of booking release schedule for venue.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique identifier of the venue to which the bookings belong
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=false %}
The unique id of the booking to which the release schedule term applies
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=false %}
The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\)
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=true %}
The number of booking release schedule to fetch
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
        "totalResults": 3,
        "start": 0,
        "perPage": 5,
        "count": 3
    },
    "results": [{
        "bookingId": 4288,
        "venueId": 166,
        "type": 1,
        "numDaysFromEvent": 10,
        "numOfRooms": 0,
        "percentageOfRooms": 5
    }, {
        "bookingId": 4288,
        "venueId": 166,
        "type": 0,
        "numDaysFromEvent": 15,
        "numOfRooms": 5,
        "percentageOfRooms": 0
    }, {
        "bookingId": 4289,
        "venueId": 166,
        "type": 0,
        "numDaysFromEvent": 15,
        "numOfRooms": 5,
        "percentageOfRooms": 0
    }]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the booking release schedule the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.