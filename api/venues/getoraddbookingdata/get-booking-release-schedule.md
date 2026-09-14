# Get Booking Release Schedule

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/venue?action=getBookingReleaseSchedule`

Get a list of booking release schedule for venue.

#### Request Body

| Name                                      | Type    | Description                                                                                                       |
| ----------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| venueId<mark style="color:red;">\*</mark> | integer | The unique identifier of the venue to which the bookings belong                                                   |
| bookingId                                 | integer | The unique id of the booking to which the release schedule term applies                                           |
| start                                     | integer | The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.) |
| perPage<mark style="color:red;">\*</mark> | integer | The number of booking release schedule to fetch                                                                   |

{% tabs %}
{% tab title="200 " %}
```
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
{% endtab %}
{% endtabs %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the booking release schedule the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.
