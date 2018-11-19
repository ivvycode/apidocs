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
|  |  |  |  |

## Reserved Room Day Rates

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
|  |  |  |  |

## Guest

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
|  |  |  |  |

## Guest Contact Details

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
|  |  |  |  |

