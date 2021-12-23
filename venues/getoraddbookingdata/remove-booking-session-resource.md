# Remove Booking Session Resource

{% swagger baseUrl="[PlatformAddress]" path="/api/1.0/venue?action=removeBookingSessionResource" method="post" summary="Remove a booking session resource" %}
{% swagger-description %}
Remove a booking session resource from the booking session
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the booking session resource belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the session resource belongs
{% endswagger-parameter %}

{% swagger-parameter name="sessionId" type="integer" in="body" %}
The unique id of the booking session to which the resource belongs
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the booking session resource to remove
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
