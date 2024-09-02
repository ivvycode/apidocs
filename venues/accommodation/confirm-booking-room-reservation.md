# Confirm Booking Room Reservation

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=confirmBookingRoomReservation" method="post" summary="Confirm Booking Room Reservation" %}
{% swagger-description %}
Confirm a room reservation on a booking.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the booking belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the room reservation belongs
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the room reservation to confirm
{% endswagger-parameter %}

{% swagger-parameter name="roomIds" type="array" in="body" %}
Optionally, the array of ids of the individual rooms on the reservation to cancel
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

## Response Error Types

| Error Type | Reason                                                                                                             |
| ---------- | ------------------------------------------------------------------------------------------------------------------ |
| 0          | Unknown error                                                                                                      |
| 1          | The reservation is already confirmed (and cannot be confirmed again)                                               |
| 2          | The reservation is cancelled (and cannot be confirmed)                                                             |
| 3          | The reservation has no rooms to confirm                                                                            |
| 4          | The accommodation group to which the room reservation applies, cannot confirm availability of the room             |
| 5          | There are not enough rooms available in the accommodation group to which the room reservation applies              |
| 6          | Unknown channel error                                                                                              |
| 7          | One or more individual rooms on the reservation cannot be confirmed                                                |
| 8          | Unknown channel error                                                                                              |
| 9          | The canBeEdited flag of the room reservation is false, which prevents any changes                                  |
| 10         | Confirming one or more room failed when roomIds parameter were set. See "failedRooms" in response for more details |

## Failed Rooms Error Codes

| Code | Message                                       |
| ---- | --------------------------------------------- |
| 1    | The room has already been confirmed           |
| 2    | The room has been cancelled                   |
| 3    | There are not enough rooms available in group |
| 4    | Room cannot be booked                         |
| 5    | The reservation cannot be edited              |
