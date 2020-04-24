# Change Status of Booking Room Reservation

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=changeStatusOfBookingRoomReservation" %}
{% api-method-summary %}
Change Status of Booking Room Reservation
{% endapi-method-summary %}

{% api-method-description %}
Change the status of a specific room reservation on a venue booking. **NOTE:** Currently this only supports changing the status to "checked in" or "checked out". Use this action to confirm a room reservation, and this one to cancel.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking belongs
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=true %}
The unique id of the booking to which the room reservation belongs
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="integer" required=true %}
The unique id of the room reservation to change status
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="integer" required=true %}
The status to which the room reservation will be changed. Only a value of 4 \(Checked In\) or 5 \(Checked Out\) are supported by this action
{% endapi-method-parameter %}

{% api-method-parameter name="roomIds" type="array" required=false %}
Optionally, the array of ids of the individual rooms on the reservation to change status
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully changing a confirmed room reservation to checked-in
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "errorType": null
}
```
{% api-method-response-example-description %}
Changing status of one or more rooms failed when roomIds were set in request
{% endapi-method-response-example-description %}

```javascript
{
  "success": false,
  "errorType": 5,
  "failedRooms": [
      {
          "id": 123,
          "errorCode": 2,
          "errorMessage": "The current status cannot transition to the new status"
      },
      {
          "id": 456,
          "errorCode": 2,
          "errorMessage": "The current status cannot transition to the new status"
      }
  ]
}
```

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Status Transitions

The following describes how the [status](get-booking-room-reservation-list.md#room-reservation-status) of a booking room reservation can transition from one status to another.

![](../../.gitbook/assets/booking-room-reservation-status-transitions.png)

NOTES:
To delete a booking room reservation, use the [Remove Booking Room Reservation](remove-booking-room-reservation.md) action.
To confirm a booking room reservation, use the [Confirm Booking Room Reservation](confirm-booking-room-reservation.md) action.
To cancel a booking room reservation, use the [Cancel Booking Room Reservation](cancel-booking-room-reservation.md) action.

## Response Error Types

| Error Type | Reason |
| :--- | :--- |
| 0 | Unknown error |
| 1 | The new status is the same as the current status |
| 2 | The current status cannot transition to the new status |
| 3 | The new status is not supported. Only "checked in" and "checked out" are supported |
| 4 | The canBeEdited flag of the room reservation is false, which prevents any changes |
| 5 | Changing status of one or more room failed when roomIds parameter were set. See "failedRooms" in response for more details |

## Failed Rooms Error Codes

| Code | Message |
| :--- | :--- |
| 1 | The new status is the same as the current status |
| 2 | The current status cannot transition to the new status |
| 3 | The new status is not supported |
| 4 | The reservation of room cannot be edited |