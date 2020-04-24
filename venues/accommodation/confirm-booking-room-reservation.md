# Confirm Booking Room Reservation

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=confirmBookingRoomReservation" %}
{% api-method-summary %}
Confirm Booking Room Reservation
{% endapi-method-summary %}

{% api-method-description %}
Confirm a room reservation on a booking.
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

{% api-method-parameter name="roomIds" type="array" required=false %}
Optionally, the array of ids of the individual rooms on the reservation to cancel
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
{% api-method-response-example-description %}
Confirming one or more rooms failed when roomIds were set in request
{% endapi-method-response-example-description %}

```javascript
{
  "success": false,
  "errorType": 10,
  "failedRooms": [
      {
          "id": 123,
          "errorCode": 2,
          "errorMessage": "The room has been cancelled"
      },
      {
          "id": 456,
          "errorCode": 2,
          "errorMessage": "The room has been cancelled"
      }
  ]
}
```

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Response Error Types

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
| 9 | The canBeEdited flag of the room reservation is false, which prevents any changes |
| 10 | Confirming one or more room failed when roomIds parameter were set. See "failedRooms" in response for more details |

## Failed Rooms Error Codes

| Code | Message |
| :--- | :--- |
| 1 | The room has already been confirmed |
| 2 | The room has been cancelled |
| 3 | There are not enough rooms available in group |
| 4 | Room cannot be booked |
| 5 | The reservation cannot be edited |

