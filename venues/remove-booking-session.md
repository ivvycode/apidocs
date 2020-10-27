# Remove Booking Session

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=removeBookingSession" %}
{% api-method-summary %}
Remove Booking Session
{% endapi-method-summary %}

{% api-method-description %}
Remove booking session from booking session
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The unique id of the booking session
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking session belongs belongs
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=true %}
The unique id of the booking to which the booking session belongs belongs
{% endapi-method-parameter %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully removing a session from the booking.
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


## Example Request

```javascript
{
  "id": 8820,
  "venueId": 1,
  "bookingId": 15722
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the session is delete from the booking |
| id | The unique id of the Booking Session |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24365 | The booking does not exist |
| Specific Code: 24366 | The session does not exist |
