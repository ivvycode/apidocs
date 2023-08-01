# Remove Booking Accommodation

{% swagger baseUrl="[PlatformAddress]" path="/api/1.0/venue?action=removeBookingAccommodation" method="post" summary="Remove Booking Accommodation" %}
{% swagger-description %}
Remove an accommodation group from a specific booking
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the booking belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the accommodation group belongs
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the accommodation group to remove
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

| Error Type | Reason                                                               |
| ---------- | -------------------------------------------------------------------- |
| 1          | Unknown error                                                        |
| 2          | The accommodation group has room reservations, and cannot be removed |
