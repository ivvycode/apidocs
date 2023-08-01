# Remove Booking Session Beverage

{% swagger baseUrl="[PlatformAddress]" path="/api/1.0/venue?action=removeBookingSessionBeverage" method="post" summary="Remove Booking Session Beverage Package" %}
{% swagger-description %}
Remove booking session beverage package from booking session
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the booking session beverage package
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the booking session beverage package belongs belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the booking session beverage package belongs belongs
{% endswagger-parameter %}

{% swagger-parameter name="sessionId" type="integer" in="body" %}
The unique id of the booking session to which the booking session beverage package belongs belongs
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
