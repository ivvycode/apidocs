# Add or Update Booking Accommodation

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=addOrUpdateBookingAccommodation" %}
{% api-method-summary %}
Add or Update Booking Accommodation
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a specific booking accommodation group on a specific venue booking. This action will fail if the booking cannot support accommodation blocks.
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
| cutOffDate | date | optional | The date after which changes to the accommodation group are not allowed |
| dayRatesActual | array of [Day Rates Actual](add-or-update-booking-accommodation.md#booking-accommodation-day-rates-actual) | optional | The daily actual rates of the accommodation group |
| dayRates | array of [Day Rates](add-or-update-booking-accommodation.md#booking-accommodation-day-rates) | required on add, optional on update | The daily rates of the accommodation group |
| excludedTaxIds | array of integers | optional | The unique ids of the taxes that are excluded from the daily rates |
| roomOptions | array of [Room Options](add-or-update-booking-accommodation.md#booking-accommodation-room-option) | optional | The additional room options of the accommodation group |

## Booking Accommodation Day Rates Actual

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| bookingDate | date | true | The actual date of the accommodation group to which the rate applies |
| numRooms | integer | true | The actual number of rooms booked on bookingDate |
| cost | number | true | The actual rate amount for the room on bookingDate. The amount either includes or excludes tax depending on how the venue is configured |
| numPayableByGuest | integer | true | The actual number of rooms on bookingDate that are payable by guests \(as opposed to the master account of the booking\) |

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

## Notes on updating an accommodation group

Updating an existing accommodation group **overlays** the existing data. Optional request data that is excluded will not change existing data. This does not guarantee that the request data will validate if other data is changed. For example, if the end date of the accommodation is extended, rates for the **new** dates will be required.

If the start and/or end dates of the accommodation group change:  
\* Any existing rates on dates that no longer apply \(i.e. _bookingDate_ is outside the new group dates\) will be removed.  
\* Any existing room options on dates that no longer apply \(i.e. _bookingDate_ is outside the new group dates\) will be removed.  
\* Rates for any new dates are required.  
\* If the accommodation group dates extend beyond the accommodation dates of the booking \(to which the group belongs\) then the booking's accommodation dates will be adjusted to include the new date range.

Day rates override existing data based on the _bookingDate_ value in the request. For example, to change the rate on 23/12/2019:  
`{    
"bookingDate": "2019-12-23",    
"numRooms": 5,    
"cost": 180,    
"numPayableByGuest": 0    
}`

Room options override existing data based on the _roomOptionId_ and _bookingDate_ values in the request.

The same room option can only be added to the accommodation group once \(this also applies when adding an accommodation group\). If a room option appears multiple times in the request for the same date, the last value is used. For example:  
`"roomOptions": [    
{    
"bookingDate", "2019-01-01",    
"roomOptionId": 124,    
"numRooms": 4,    
"numOptionsPerRoom": 1,    
"price": 25,    
"excludedTaxIds": [],    
"numPayableByGuest": 0    
},    
{    
"bookingDate", "2019-01-01",    
"roomOptionId": 124,    
"numRooms": 6,    
"numOptionsPerRoom": 2,    
"price": 30,    
"excludedTaxIds": [],    
"numPayableByGuest": 0    
}    
]`  
_roomOptionId_ 124 on 01/01/2019 will have: numRooms 6, numOptionsPerRoom 2, price 30 etc.

To remove room options from an accommodation group, pass zero values as follows:  
`{    
"bookingDate": "2019-01-01",    
"roomOptionId": 124,    
"numRooms": 0,    
"numOptionsPerRoom": 0,    
"price": 0,    
"excludedTaxIds": [],    
"numPayableByGuest": 0    
}`

The _numRooms_ & _numPayableByGuest_ values of a room option cannot exceed the _numRooms_ value on the same _bookingDate_. For example, if the following day rate exists:  
`{    
"bookingDate": "2019-12-23",    
"numRooms": 5,    
"cost": 180,    
"numPayableByGuest": 0    
}`  
Then the _numRooms_ & _numPayableByGuest_ values of any room option on 23/12/2019 cannot exceed 5. It is possible to update an existing accommodation group and either decrease or increase _numRooms_ of the day rate. If the day rate _numRooms_ is decreased, all existing room options that exceed the new value will also be decreased. If the day rate _numRooms_ is increased, no existing room options are modified \(unless the new values are passed in the request\).

