# Confirm Booking Room Reservation

**NOTE: This action has not been published**

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=confirmBookingRoomReservation" %}
{% api-method-summary %}
Confirm Booking Room Reservation
{% endapi-method-summary %}

{% api-method-description %}
Confirm a room reservation on a booking. Once a room reservation is confirmed, no other updates are allowed.
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
The unique id of the room reservation to confirm
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully confirming a room reservation from a booking
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
| 0 | Unknown error |
| 1 | The reservation is already confirmed \(and cannot be confirmed again\) |
| 2 | The reservation is cancelled \(and cannot be confirmed\) |
| 3 | The reservation has no rooms to confirm |
| 4 | The accommodation group to which the room reservation applies, cannot confirm availability of the room |
| 5 | There are not enough rooms available in the accommodation group to which the room reservation applies |
| 6 | Unknown channel error |
| 7 | One or more individual rooms on the reservation cannot be confirmed |
| 8 | Unknown channel error |



