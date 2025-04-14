# Remove Booking Room Reservation

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=removeBookingRoomReservation" method="post" summary="Remove Booking Room Reservation" %}
{% swagger-description %}
Remove a room reservation from a specific booking. The booking must satisfy the following:

\


\* Accommodation is included.

\


\* The status must be "confirmed".
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the booking belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the room reservation belongs
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the room reservation to remove
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

| Error Type | Reason                                                |
| ---------- | ----------------------------------------------------- |
| 1          | Unknown error                                         |
| 2          | Only "not confirmed" room reservations can be deleted |
