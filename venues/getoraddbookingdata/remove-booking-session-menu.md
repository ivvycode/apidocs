# Remove Booking Session Menu

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=removeBookingSessionMenu" method="post" summary="Remove Booking Session Menu" %}
{% swagger-description %}
Remove booking session menu from booking session
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the booking session menu
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the booking session menu belongs belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the booking session menu belongs belongs
{% endswagger-parameter %}

{% swagger-parameter name="sessionId" type="integer" in="body" %}
The unique id of the booking session to which the booking session menu belongs belongs
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "success": true,
  "id": 1234
}
```
{% endswagger-response %}
{% endswagger %}
