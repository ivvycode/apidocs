# Change Status of Booking Room Reservation

{% swagger baseUrl="[PlatformAddress]" path="/api/1.0/venue?action=changeStatusOfBookingRoomReservation" method="post" summary="Change Status of Booking Room Reservation" %}
{% swagger-description %}
Change the status of a specific room reservation on a venue booking. 

**NOTE:**

 Currently this only supports changing the status to "checked in" or "checked out". Use this action to confirm a room reservation, and this one to cancel.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the booking belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the room reservation belongs
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the room reservation to change status
{% endswagger-parameter %}

{% swagger-parameter name="status" type="integer" in="body" %}
The status to which the room reservation will be changed. Only a value of 4 (Checked In) or 5 (Checked Out) are supported by this action
{% endswagger-parameter %}

{% swagger-parameter name="roomIds" type="array" in="body" %}
Optionally, the array of ids of the individual rooms on the reservation to change status
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "success": true,
  "errorType": null
}
```
{% endswagger-response %}
{% endswagger %}

## Status Transitions

The following describes how the [status](get-booking-room-reservation-list.md#room-reservation-status) of a booking room reservation can transition from one status to another.

![](<../../.gitbook/assets/booking-room-reservation-status-transitions (1).png>)

NOTES: To delete a booking room reservation, use the [Remove Booking Room Reservation](remove-booking-room-reservation.md) action. To confirm a booking room reservation, use the [Confirm Booking Room Reservation](confirm-booking-room-reservation.md) action. To cancel a booking room reservation, use the [Cancel Booking Room Reservation](cancel-booking-room-reservation.md) action.

## Response Error Types

| Error Type | Reason                                                                                                                     |
| ---------- | -------------------------------------------------------------------------------------------------------------------------- |
| 0          | Unknown error                                                                                                              |
| 1          | The new status is the same as the current status                                                                           |
| 2          | The current status cannot transition to the new status                                                                     |
| 3          | The new status is not supported. Only "checked in" and "checked out" are supported                                         |
| 4          | The canBeEdited flag of the room reservation is false, which prevents any changes                                          |
| 5          | Changing status of one or more room failed when roomIds parameter were set. See "failedRooms" in response for more details |

## Failed Rooms Error Codes

| Code | Message                                                |
| ---- | ------------------------------------------------------ |
| 1    | The new status is the same as the current status       |
| 2    | The current status cannot transition to the new status |
| 3    | The new status is not supported                        |
| 4    | The reservation of room cannot be edited               |
