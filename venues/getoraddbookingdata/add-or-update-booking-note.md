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
| bookingDays | array | optional | The days of the booking. Required when typeId is one of 3 11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,29,30,31,32,33,34,35,36,37 |
| accommodationIds | array | optional | The array of an ids of the booking accommodation. Required when typeId = TYPE_BOOKING_ACCOMMODATION |
| sessionIds | array | optional | The array of an ids of the booking session. Required when typeId = TYPE_SESSION|
| menuIds | array | optional | The array of an ids of the booking session menu. Required when typeId = TYPE_SESSION_MENU |
| beverageIds | array | optional | The array of an ids of the booking beverage. Required when typeId = TYPE_SESSION_BEVERAGE|
| resourceIds | array | optional | The array of an ids of the booking resource. Required when typeId = TYPE_SESSION_RESOURCE |
| productIds | array | optional | The array of an ids of the booking product. Required when typeId = TYPE_SESSION_PRODUCT|
| applyToTemplates | array | optional | The ['Template Applies To'](add-or-update-booking-note.md#template-applies-to) in booking notes. |


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
| 3 | Billing Instructions |
| 8 | Accommodation |
| 11 | Couriers |
| 12 | VIP Guests |
| 13 | Security |
| 14 | Onsite Contractors |
| 15 | Signatories |
| 16 | Front Office |
| 17 | Transfers |
| 18 | Room Drops |
| 19 | Laguage Services |
| 20 | Group Profile |
| 21 | Lead |
| 2 | Session |
| 4 | Menu |
| 5 | Beverage |
| 7 | Products |
| 6 | Resources |
| 22 | Dietary Requirements |
| 23 | All Departments |
| 24 | Food & Beverages |
| 25 | Car Parking |
| 26 | Suppliers |
| 27 | Internet |
| 29 | Signage |
| 30 | Sales office |
| 31 | Bellman / Van Service |
| 32 | Reservations |
| 33 | Housekeeping |
| 34 | Engineering |
| 35 | Audio Visual |
| 36 | Set-up |
| 37 | Onsite Contat |

## Template Applies To
| Type | Description |
| :--- | :--- |
| 1 | Beo |
| 2 | Quotes & Contracts |
| 3 | Resume |