# Change Status of Booking Room Reservation

**NOTE: This action has not been published**

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=changeStatusOfBookingRoomReservation" %}
{% api-method-summary %}
Change Status of Booking Room Reservation
{% endapi-method-summary %}

{% api-method-description %}
Change the status of a specific room reservation on a venue booking. **NOTE:** Currently this only supports changing the status to "checked in" or "checked out". Use this action to confirm a room reservation, and this one to cancel.
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
The unique id of the room reservation to change status
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="integer" required=true %}
The [status](get-booking-room-reservation-list.md#room-reservation-status) to which the room reservation will be changed
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully changing a confirmed room reservation to checked-in
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
| 1 | The new status is the same as the current status |
| 2 | The current status cannot transition to the new status |
| 3 | The new status is not supported. Only "checked in" and "checked out" are supported |

