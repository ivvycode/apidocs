# Get Booking Accommodation List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getBookingAccommodationList" path="" %}
{% api-method-summary %}
Get Booking Accommodation List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of booking accommodation for venue.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique identifier of the venue to which the bookings belong
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=false %}
The unique id of the booking to which the accommodation belongs
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=false %}
 The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\)
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=true %}
The number of booking accomodation to fetch
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
	"meta": {
		"totalResults": 1,
		"start": 0,
		"perPage": 5,
		"count": 1
	},
	"results": [{
		"bookingId": 4304,
		"venueId": 178,
		"barId": null,
		"roomId": 76,
		"startDate": "2018-08-27",
		"endDate": "2018-08-31",
		"overrideCapacity": true,
		"costcenterId": 1376,
		"dayRates": [{
			"date": "2018-08-27",
			"numRooms": 11,
			"cost": 180,
			"numRoomsPaidByGuest": 11
		}, {
			"date": "2018-08-28",
			"numRooms": 12,
			"cost": 190,
			"numRoomsPaidByGuest": 12
		}, {
			"date": "2018-08-29",
			"numRooms": 13,
			"cost": 175,
			"numRoomsPaidByGuest": 13
		}, {
			"date": "2018-08-30",
			"numRooms": 14,
			"cost": 210,
			"numRoomsPaidByGuest": 14
		}],
		"taxes": [],
		"roomExtras": [{
			"date": "2018-08-27",
			"optionId": 35,
			"numRooms": 11,
			"numOptionsPerRoom": 1,
			"price": 65,
			"taxes": [],
			"costcenterId": 1377,
			"numPaidByGuest": 11
		}, {
			"date": "2018-08-30",
			"optionId": 36,
			"numRooms": 10,
			"numOptionsPerRoom": 1,
			"price": 80,
			"taxes": [],
			"costcenterId": 1377,
			"numPaidByGuest": 10
		}],
		"modifiedDate": "2018-08-22 06:43:24 UTC"
	}]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the booking accomodation the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

