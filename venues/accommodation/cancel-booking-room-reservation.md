# Cancel Booking Room Reservation

{% swagger baseUrl="[PlatformAddress]" path="/api/1.0/" path="venue?action=cancelBookingRoomReservation" method="post" summary="Cancel Booking Room Reservation" %}
{% swagger-description %}
Cancel a room reservation on a booking. Only reservations that are "not confirmed" can be cancelled.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the booking belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the room reservation belongs
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the room reservation to cancel
{% endswagger-parameter %}

{% swagger-parameter name="roomId" type="integer" in="body" %}
_DEPRECATED: Use roomIds instead_

 Optionally, the unique id of the individual room on the reservation to cancel
{% endswagger-parameter %}

{% swagger-parameter name="roomIds" type="array" in="body" %}
Optionally, the array of ids of the individual rooms on the reservation to cancel
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "success": true,
  "errorType": null,
  "failedRooms": []
}
```
{% endswagger-response %}
{% endswagger %}

## Response Error Types

| Error Type | Reason                                                                                                                                                           |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0          | Unknown error                                                                                                                                                    |
| 1          | The reservation is already cancelled (and cannot be cancelled again)                                                                                             |
| 2          | An old error condition that has been removed                                                                                                                     |
| 3          | Unknown channel error                                                                                                                                            |
| 4          | Unknown channel error                                                                                                                                            |
| 5          | One or more individual rooms on the reservation cannot be cancelled                                                                                              |
| 6          | The status of the reservation prevents it from being cancelled. Only "not confirmed", "confirmed", "checked in", and "checked out" reservations can be cancelled |
| 7          | The canBeEdited flag of the room reservation is false, which prevents any changes                                                                                |
| 8          | Cancelling one or more room failed when roomIds parameter were set. See "failedRooms" in response for more details                                               |

## Failed Rooms Error Codes

| Code | Message                                      |
| ---- | -------------------------------------------- |
| 1    | The room has already been cancelled          |
| 2    | The room cannot be cancelled                 |
| 3    | The reservation of the room cannot be edited |
