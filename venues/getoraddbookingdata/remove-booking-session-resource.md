# Remove Booking Session Resource

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=removeBookingSessionResource" %}
{% api-method-summary %}
Remove a booking session resource
{% endapi-method-summary %}

{% api-method-description %}
Remove a booking session resource from the booking session
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking session resource belongs
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=true %}
The unique id of the booking to which the session resource belongs
{% endapi-method-parameter %}

{% api-method-parameter name="sessionId" type="integer" required=true %}
The unique id of the booking session to which the resource belongs
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="integer" required=true %}
The unique id of the booking session resource to remove
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully removing an booking session resource from the booking session
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

