# Get Booking Notes

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getBookingNoteList" method="post" summary="Get Booking Note List" %}
{% swagger-description %}
Get a list of booking notes.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="path" %}
The id of the bookng
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of booking notes to get in a single call
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 5,
        "start": 0,
        "perPage": 50,
        "count": 2
    },
    "results": [
        {
            "id": 409,
            "venueId": 1,
            "bookingId": 7192,
            "isPrivate": false,
            "description": "<p>Some note for Booking Accommodation</p> ",
            "typeId": 8,
            "createdBy": 1,
            "createdDate": "2017-07-12 07:05:24 UTC",
            "modifiedDate": "2017-07-12 07:05:24 UTC"
        },
        {
            "id": 434,
            "venueId": 1,
            "bookingId": 7192,
            "isPrivate": false,
            "description": "<p>A note for booking session</p> ",
            "typeId": 2,
            "createdBy": 1,
            "createdDate": "2017-10-31 13:29:13 UTC",
            "modifiedDate": "2017-10-31 13:29:13 UTC"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific Booking's notes List`

```javascript
{
  "venueId": "1",
    "bookingId": "7192",
    "perPage": "50",
}
```

## Booking Notes

| Property     | Type     | Description                                            |
| ------------ | -------- | ------------------------------------------------------ |
| id           | integer  | The unique id of the booking note                      |
| venueId      | integer  | The unique id of the venue to which the note belongs   |
| bookingId    | integer  | The unique id of the booking to which the note belongs |
| isPrivate    | boolean  | Whether or not the booking note is private             |
| description  | text     | The description of the booking note                    |
| typeId       | integer  | The type of the booking note                           |
| createdBy    | integer  | The unique id of user who created the booking note     |
| createdDate  | datetime | The date & time the booking note was created           |
| modifiedDate | datetime | The date & time the booking note was last modified     |

## typeId:

One of the following values:

* No Type = 0
* Type Booking = 1
* Type Session = 2
* Type Billing = 3
* Type Session Menu = 4
* Type Session Beverage = 5
* Type Session Resources = 6
* Type Session Products = 7
* Type Booking Accommodation = 8
* Type Contact = 9
* Type Company = 10
* Type Couriers = 11
* Type Vip Guests = 12
* Type Security = 13
* Type Onsite Contractors = 14
* Type Signatories = 15
* Type Front Offices = 16
* Type Transfers = 17
* Type Room Drops = 18
* Type Luggage Services = 19
* Type Group Profile = 20
* Type Lead = 21
* Type Lead Original = -1 // Used Do Display Lead Notes @see Model Crm Lead Note
* Type Dietary Requirements = 22
* Type All Departments = 23
* Type Food And Beverage = 24
* Type Car Parking = 25
* Type Suppliers = 26
* Type Internet = 27
* Type Lead Description = 28
* Type Signage = 29
* Type Sales Office = 30
* Type Bellman Van Service = 31
* Type Reservation = 32
* Type Housekeeping = 33
* Type Engineering = 34

## Additional Parameters

| Property     | Description             | Type                                                                     |
| ------------ | ----------------------- | ------------------------------------------------------------------------ |
| createdDate  | Filter by Created Date  | [iVvy Timestamp Format](../../development-reference/timestamp-format.md) |
| modifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../../development-reference/timestamp-format.md) |

## Additional [Filter](../../getting-started/interpreting-the-response/filtering.md) Properties

| Property    | Description                               | Type    |
| ----------- | ----------------------------------------- | ------- |
| isPrivate   | Filter notes whether it is private or not | boolean |
| description | Filter by description of notes type       | string  |
| typeId      | Filter by unique id of notes type         | integer |
| createdBy   | Filter by user who created note           | integer |
