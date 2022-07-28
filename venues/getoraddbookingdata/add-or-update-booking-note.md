# Add or Update Booking Note

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=addOrUpdateBookingNote" %}
{% api-method-summary %}
Add or Update Booking Note
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a venue booking note.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the booking note to add or update. See below for the data description.
{% endapi-method-request %}

{% endapi-method-spec %}
{% endapi-method %}

## Booking Note

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the booking note to update. If property is omitted, it will create a new note |
| venueId | integer | required | The id of the venue to which the booking note belongs |
| bookingId | integer | required | The id of the booking to which the booking note will be assigned. |
| description | string | required | The description of the booking note. |
| isPrivate | bool | optional | Whether or not the booking note is accessible to all. |
| typeId | integer | optional | The [type](add-or-update-booking-note.md#booking-note-type) of the booking note. |
| bookingDays | array | optional | The days of the booking. Required when typeId is one of [type](add-or-update-booking-note.md#booking-note-type-for-bookingdays) |
| accommodationIds | array | optional | The array of an ids of the booking accommodation. Required when typeId = TYPE_BOOKING_ACCOMMODATION |
| sessionIds | array | optional | The array of an ids of the booking session. Required when typeId = TYPE_SESSION|
| menuIds | array | optional | The array of an ids of the booking session menu. Required when typeId = TYPE_SESSION_MENU |
| beverageIds | array | optional | The array of an ids of the booking beverage. Required when typeId = TYPE_SESSION_BEVERAGE|
| resourceIds | array | optional | The array of an ids of the booking resource. Required when typeId = TYPE_SESSION_RESOURCE |
| productIds | array | optional | The array of an ids of the booking product. Required when typeId = TYPE_SESSION_PRODUCT|
| applyToTemplates | array | optional | The 'Template Applies To' in booking notes. |


## Example Request

```javascript
{
    "id": 5,
    "venueId": 1,
    "bookingId": 110,
    "description": "test description",
    "typeId": 23,
    "bookingDays": [1,2],
    "applyToTemplates": [1,2]
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the booking attendee was added/updated |
| id | The unique id of the booking attendee that was added/updated |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24442 | The booking note does not exist |
| Specific Code: 24443 | An error has occurred |
| Specific Code: 24444 | The request contains invalid data |
| Specific Code: 24445 | The request contains invalid data |

## Booking Note Type
| Type | Description |
| :--- | :--- |
| 3 | TYPE_BILLING |
| 8 | TYPE_BOOKING_ACCOMMODATION |
| 11 | TYPE_COURIERS |
| 12 | TYPE_VIP_GUESTS |
| 13 | TYPE_SECURITY |
| 14 | TYPE_ONSITE_CONTRACTORS |
| 15 | TYPE_SIGNATORIES |
| 16 | TYPE_FRONT_OFFICES |
| 17 | TYPE_TRANSFERS |
| 18 | TYPE_ROOM_DROPS |
| 19 | TYPE_LUGGAGE_SERVICES |
| 20 | TYPE_GROUP_PROFILE |
| 21 | TYPE_LEAD |
| 2 | TYPE_SESSION |
| 4 | TYPE_SESSION_MENU |
| 5 | TYPE_SESSION_BEVERAGE |
| 7 | TYPE_SESSION_PRODUCTS |
| 6 | TYPE_SESSION_RESOURCES |
| 22 | TYPE_DIETARY_REQUIREMENTS |
| 23 | TYPE_ALL_DEPARTMENTS |
| 24 | TYPE_FOOD_AND_BEVERAGE |
| 25 | TYPE_CAR_PARKING |
| 26 | TYPE_SUPPLIERS |
| 27 | TYPE_INTERNET |
| 29 | TYPE_SIGNAGE |
| 30 | TYPE_SALES_OFFICE |
| 31 | TYPE_BELLMAN_VAN_SERVICE |
| 32 | TYPE_RESERVATION |
| 33 | TYPE_HOUSEKEEPING |
| 34 | TYPE_ENGINEERING |
| 35 | TYPE_AUDIO_VISUAL |
| 36 | TYPE_SETUP |
| 37 | TYPE_ONSITE_CONTACT |

## Booking Note Type for bookingDays
| Type | Description |
| :--- | :--- |
| 3 | TYPE_BILLING |
| 11 | TYPE_COURIERS |
| 12 | TYPE_VIP_GUESTS |
| 13 | TYPE_SECURITY |
| 14 | TYPE_ONSITE_CONTRACTORS |
| 15 | TYPE_SIGNATORIES |
| 16 | TYPE_FRONT_OFFICES |
| 17 | TYPE_TRANSFERS |
| 18 | TYPE_ROOM_DROPS |
| 19 | TYPE_LUGGAGE_SERVICES |
| 20 | TYPE_GROUP_PROFILE |
| 21 | TYPE_LEAD |
| 22 | TYPE_DIETARY_REQUIREMENTS |
| 23 | TYPE_ALL_DEPARTMENTS |
| 24 | TYPE_FOOD_AND_BEVERAGE |
| 25 | TYPE_CAR_PARKING |
| 26 | TYPE_SUPPLIERS |
| 27 | TYPE_INTERNET |
| 29 | TYPE_SIGNAGE |
| 30 | TYPE_SALES_OFFICE |
| 31 | TYPE_BELLMAN_VAN_SERVICE |
| 32 | TYPE_RESERVATION |
| 33 | TYPE_HOUSEKEEPING |
| 34 | TYPE_ENGINEERING |
| 35 | TYPE_AUDIO_VISUAL |
| 36 | TYPE_SETUP |
| 37 | TYPE_ONSITE_CONTACT |