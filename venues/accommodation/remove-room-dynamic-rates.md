# Remove Room Dynamic Rates

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=removeRoomDynamicRates" path="" %}
{% api-method-summary %}
Remove Room Dynamic Rates
{% endapi-method-summary %}

{% api-method-description %}
Remove one or more dynamic rates from venue rooms.
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
The start date from which the dynamic rate will be removed \(Date Format\)
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="string" required=true %}
The end date until which the dynamic rate will be removed \(Date Format\)
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

### Remove the room dynamic rates from a single date

```javascript
{
  "venueId": 123
  "barId": 456
  "roomId": 789
  "startDate": "2018-07-27"
  "endDate": "2018-07-27"
}
```

### Remove the room dynamic rates from multiple dates

```javascript
{
  "venueId": 123
  "barId": 456
  "roomId": 789
  "startDate": "2018-07-27"
  "endDate": "2018-08-03"
}
```

## Returns

| Property | Description | Type |
| :--- | :--- | :--- |
| success | Whether or not the room dynamic rates were removed | boolean |

