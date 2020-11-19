# Remove Booking Session Beverage

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=removeBookingSessionBeverage" %}
{% api-method-summary %}
Remove Booking Session Beverage Package
{% endapi-method-summary %}

{% api-method-description %}
Remove booking session beverage package from booking session
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The unique id of the booking session beverage package
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking session beverage package belongs belongs
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=true %}
The unique id of the booking to which the booking session beverage package belongs belongs
{% endapi-method-parameter %}

{% api-method-parameter name="sessionId" type="integer" required=true %}
The unique id of the booking session to which the booking session beverage package belongs belongs
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully removing an blockout space from a function diary.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 1234
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

