# Cancel Booking Room Reservation

**NOTE: This action has not been published**

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
  "errorType": null
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

| Error Type | Reason |
| :--- | :--- |
| 0 | Unknown error |
| 1 | The reservation is already cancelled \(and cannot be cancelled again\) |
| 2 | Only "confirmed" reservations can be cancelled |
| 3 | Unknown channel error |
| 4 | Unknown channel error |
| 5 | One or more individual rooms on the reservation cannot be cancelled |

