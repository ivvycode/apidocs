# Add or Update Room Dynamic Rates

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateRoomDynamicRates" path="" %}
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

{% api-method-parameter name="barId" type="integer" required=true %}
The unique id of the rate plan to which the dynamic rate applies
{% endapi-method-parameter %}

{% api-method-parameter name="roomId" type="integer" required=true %}
The unique id of the room to which the rate applies
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="string" required=true %}
The start date from which the dynamic rate will be set
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="string" required=true %}
The end date from which the dynamic rate will be set
{% endapi-method-parameter %}

{% api-method-parameter name="cost" type="number" required=true %}
The rate amount from startDate to endDate. The amount must either include or exclude tax depending on how the venue has been configured
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
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
  "venueId": 123,
  "barId": 456,
  "roomId": 789,
  "startDate": "2018-07-27",
  "endDate": "2018-07-27",
  "cost": 240.00
}
```

### Setting the room dynamic rate for a date range

```javascript
{
  "venueId": 123,
  "barId": 456,
  "roomId": 789,
  "startDate": "2018-07-27",
  "endDate": "2018-08-03",
  "cost": 234.50
}
```

## Returns

| Property | Description | Type |
| --- | --- | --- |
| success | Whether or not the room dynamic rates were updated | boolean |

