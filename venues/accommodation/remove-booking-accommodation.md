# Remove Booking Accommodation

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=removeBookingAccommodation" %}
{% api-method-summary %}
Remove Booking Accommodation
{% endapi-method-summary %}

{% api-method-description %}
Remove an accommodation group from a specific booking
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking belongs
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=true %}
The unique id of the booking to which the accommodation group belongs
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="integer" required=true %}
The unique id of the accommodation group to remove
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully removing an accommodation group from a booking.
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
| 2 | The accommodation group has room reservations, and cannot be removed |

