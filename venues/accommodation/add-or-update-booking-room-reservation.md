# Add or Update Booking Room Reservation

**NOTE: This action has not been published**

{% api-method method="post" host="\[PlatformAddress\]" path=" /api/1.0/venue?action=addOrUpdateBookingRoomReservation" %}
{% api-method-summary %}
Add or Update Booking Room Reservation
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a specific room reservation on a specific venue booking. The booking must satisfy the following:  
\* Accommodation is included, and the booking has accommodation groups.  
\* The status must be "confirmed".
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the room reservation to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 123,
  "reference": "45",
  "mainGuest": {
    "id": 101,
    "contactId": 43213
  },
  "rooms": [
    {
      "id": 4001,
      "guest": {
        "id": 101,
        "contactId": 43213
      }
    },
    {
      "id": 4002,
      "guest": {
        "id": 102,
        "contactId": 44321
      }
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid request data that prevents the room reservation from being added/updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 400,
  "message": "The request contains invalid data",
  "specificCode": 24257,
  "additionalMessages": [
      "firstName: Value is required and can't be empty"
  ],
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Booking Room Reservation

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the room reservation to update - a new room reservation will be created if this parameter is not present |
| venueId | integer | required | The unique id of the venue to which the booking belongs |
| bookingId | integer | required | The unique id of the booking to which the room reservation belongs |
| mainGuest | [Guest](add-or-update-booking-room-reservation.md#guest) | required on add, optional on update | Details of the main guest of the room reservation |
| rooms | array of [Reserved Rooms](add-or-update-booking-room-reservation.md#reserved-room) | required on add, optional on update | Details of the individually reserved rooms on the reservation |
| removeRooms | array of integers | optional | The unique id of the individual rooms to remove from an existing reservation |

## Reserved Room

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the individual reserved room on the reservation to update. Omit this to create a new room on the reservation |
| guest | [Guest](add-or-update-booking-room-reservation.md#guest) | required on add, optional on update | Details of the guest on the individual reservation room |
| groupId | integer | required on add, optional on update | The unique id of the [accommodation group](add-or-update-booking-accommodation.md#booking-accommodation-group) from which the room is reserved |
| arrivalDate | date | required on add, optional on update | The arrival date of the reserved room |
| departureDate | date | required on add, optional on update | The departure date of the reserved room |
| excludedTaxIds | array of integers | optional | The unique ids of the taxes that are excluded from the daily rates |
| numAdultGuests | integer | required on add, optional on update | The number of adults on the reserved room. The value cannot exceed 10 |
| numChildGuests | integer | required on add, optional on update | The number of children on the reserved room. The value cannot exceed 10 |
| dayRates | array of [Day Rates](add-or-update-booking-room-reservation.md#reserved-room-day-rates) | required on add, optional on update | The daily rates of the reserved room |

## Reserved Room Day Rates

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| dayDate | date | required | The date of the reserved room to which the rate applies |
| cost | number | required | The rate amount for the reserved room on dayDate. The amount either includes or excludes tax depending on how the venue is configured |

## Guest

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the venue guest to update |
| contact | [Contact](add-or-update-booking-room-reservation.md#guest-contact-details) | required on add, optional on update | The contact details of the guest |
| primaryPhone | string | optional | The primary phone number of the guest |
| address | [Address](../../development-reference/address-format.md) | optional | The address of the guest |

## Guest Contact Details

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| firstName | string | required | The first name of the contact |
| lastName | string | required | The last name of the contact |
| email | string | required | The email address of the contact |
| phone | string | optional | The mobile phone number of the contact |

