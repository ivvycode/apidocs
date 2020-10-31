# Cancel Booking Room Reservation

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=cancelBookingRoomReservation" %}
{% api-method-summary %}
Cancel Booking Room Reservation
{% endapi-method-summary %}

{% api-method-description %}
Cancel a room reservation on a booking. Only reservations that are "not confirmed" can be cancelled.
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
The unique id of the room reservation to cancel
{% endapi-method-parameter %}

{% api-method-parameter name="roomId" type="integer" required=false %}
_DEPRECATED: Use roomIds instead_ Optionally, the unique id of the individual room on the reservation to cancel
{% endapi-method-parameter %}

{% api-method-parameter name="roomIds" type="array" required=false %}
Optionally, the array of ids of the individual rooms on the reservation to cancel
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully cancelling a room reservation from a booking
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "errorType": null,
  "failedRooms": []
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Response Error Types

| Error Type | Reason |
| :--- | :--- |
| 0 | Unknown error |
| 1 | The reservation is already cancelled \(and cannot be cancelled again\) |
| 2 | An old error condition that has been removed |
| 3 | Unknown channel error |
| 4 | Unknown channel error |
| 5 | One or more individual rooms on the reservation cannot be cancelled |
| 6 | The status of the reservation prevents it from being cancelled. Only "not confirmed", "confirmed", "checked in", and "checked out" reservations can be cancelled |
| 7 | The canBeEdited flag of the room reservation is false, which prevents any changes |
| 8 | Cancelling one or more room failed when roomIds parameter were set. See "failedRooms" in response for more details |

## Failed Rooms Error Codes

| Code | Message |
| :--- | :--- |
| 1 | The room has already been cancelled |
| 2 | The room cannot be cancelled |
| 3 | The reservation of the room cannot be edited |

