# Add or Update Booking Accommodation

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=addOrUpdateBookingAccommodation" %}
{% api-method-summary %}
Add or Update Booking Accommodation
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a specific booking accommodation group on a specific venue booking.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the accommodation group to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation.
{% endapi-method-response-example-description %}
```javascript
{
  "success": true,
  "id": 1423
}
```
{% endapi-method-response-example %}
{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid request data that prevents the accommodation group from being added/updated.
{% endapi-method-response-example-description %}
```javascript
{
  "errorCode": 400,
  "message": "The request contains invalid data",
  "specificCode": 24248,
  "additionalMessages": [
      "2019-01-01: The number of rooms can't exceed 30"
  ],
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Booking Accommodation \(Group\)

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the booking accommodation to update - a new accommodation group will be created if this parameter is not present |
| venueId | integer | required | The unique id of the venue to which the booking belongs |
| bookingId | integer | required | The unique id of the booking to which the accommodation group belongs |
| roomVenueId | integer | required | The unique id of the venue to which the rate plan \(barId\) and room type \(roomId\) belong \(can be different to venueId\) |
| barId | integer | optional | The unique id of the rate plan assigned to the accommodation group |
| roomId | integer | required | The unique id of the room type assigned to the accommodation group |
| startDate | date | required | The arrival date of the accommodation group |
| endDate | date | required | The departure date of the accommodation group |
| overrideCapacity | boolean | optional | Whether or not the accommodation group can exceed the general room availability |
| dayRates | array of [Day Rates](get-booking-accommodation-list.md#booking-accommodation-day-rates) | required on add, optional on update | The daily rates of the accommodation group |
| excludedTaxIds | array of integers | optional | The unique ids of the taxes that are excluded from the daily rates |
| roomOptions | array of [Room Options](get-booking-accommodation-list.md#booking-accommodation-room-option) | optional | The additional room options of the accommodation group |

## Booking Accommodation Day Rates

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| bookingDate | date | true | The date of the accommodation group to which the rate applies |
| numRooms | integer | true | The number of rooms booked on bookingDate |
| cost | number | true | The rate amount for the room on bookingDate. The amount either includes or excludes tax depending on how the venue is configured |
| numPayableByGuest | integer | true | The number of rooms on bookingDate that are payable by guests \(as opposed to the master account of the booking\) |

## Booking Accommodation Room Option

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| bookingDate | date | required | The date of the accommodation group to which the additional option applies |
| roomOptionId | integer | required | The unique id of the room option added on bookingDate |
| numRooms | integer | required | The number of rooms on bookingDate to which the room option applies |
| numOptionsPerRoom | integer | required | The number options added to each room \(numRooms\) on bookingDate |
| price | number | required | The price of the additional option. The amount either includes or excludes tax depending on how the venue is configured |
| excludedTaxIds | array of integers | optional | The unique ids of the taxes that are excluded from price |
| costcenterId | integer | optional | The unique id of the cost center assigned to the additional option |
| numPayableByGuest | integer | required | The number of additional options on bookingDate that are payable by guests \(as opposed to the master account of the booking\) |
