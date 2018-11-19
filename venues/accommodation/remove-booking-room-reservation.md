# Remove Booking Room Reservation

**NOTE: This action has not been published**

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=removeBookingRoomReservation" %}
{% api-method-summary %}
Remove Booking Room Reservation
{% endapi-method-summary %}

{% api-method-description %}
Remove a room reservation from a specific booking
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
The unique id of the room reservation to remove
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully removing a room reservation from a booking
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
| 1 | Unknown error |
| 2 | Only "not confirmed" room reservations can be deleted |

