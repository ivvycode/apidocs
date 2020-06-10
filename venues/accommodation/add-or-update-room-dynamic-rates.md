# Add or Update Room Dynamic Rates

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateRoomDynamicRatesCollection" path="" %}
{% api-method-summary %}
Add or Update Room Dynamics Rates
{% endapi-method-summary %}

{% api-method-description %}
Add or update the dynamic rates of venue rooms
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the rate plan belongs
{% endapi-method-parameter %}

{% api-method-parameter name="items" type="array" required=true %}
The array of items. See Item table below for individual item data.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

NOTE: The dynamic data is only available to venues that integrate with a distribution channel.

## Examples

### Setting the room dynamic rate for a single date

```javascript
{
	"venueId": 1,
	"items": [
		{
			"startDate": "2020-05-01",
			"endDate": "2020-05-01",
			"roomId": 2,
			"barId": 1,
			"cost": 100
		}
	]
}
```

### Setting the room dynamic rate for a date range

```javascript
{
	"venueId": 1,
	"items": [
		{
			"startDate": "2020-05-01",
			"endDate": "2020-05-10",
			"roomId": 2,
			"barId": 1,
			"cost": 100
		},
		{
			"startDate": "2020-05-01",
			"endDate": "2020-05-10",
			"roomId": 2,
			"barId": 147,
			"cost": 150
		},
		{
			"startDate": "2020-05-01",
			"endDate": "2020-05-10",
			"roomId": 3,
			"barId": 1,
			"cost": 100
		},
		{
			"startDate": "2020-05-01",
			"endDate": "2020-05-10",
			"roomId": 3,
			"barId": 147,
			"cost": 100
		}
	]
}
```

## Returns

| Property | Description | Type |
| :--- | :--- | :--- |
| success | Whether or not the room dynamic rates were updated | boolean |

## Item Details

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| barId | integer | required | The unique id of the rate plan to which the dynamic rate applies |
| roomId | integer | required | The unique id of the room to which the rate applies |
| startDate | date | required | The start date from which the dynamic rate will be set (Date Format) |
| endDate | date | required | The end date from which the dynamic rate will be set (Date Format) |
| cost | integer | required | The rate amount from startDate to endDate. The amount must either include or exclude tax depending on how the venue has been configured |