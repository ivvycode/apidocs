# Remove Room Dynamic Rates

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=removeRoomDynamicRates" method="post" summary="Remove Room Dynamic Rates" %}
{% swagger-description %}
Remove one or more dynamic rates from venue rooms.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the rate plan belongs
{% endswagger-parameter %}

{% swagger-parameter name="barId" type="integer" in="path" %}
The unique id of the rate plan to which the dynamic rate applies
{% endswagger-parameter %}

{% swagger-parameter name="roomId" type="integer" in="path" %}
The unique id of the room to which the rate applies
{% endswagger-parameter %}

{% swagger-parameter name="startDate" type="string" in="path" %}
The start date from which the dynamic rate will be removed (Date Format)
{% endswagger-parameter %}

{% swagger-parameter name="endDate" type="string" in="path" %}
The end date until which the dynamic rate will be removed (Date Format)
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true
}
```
{% endswagger-response %}
{% endswagger %}

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

| Property | Description                                        | Type    |
| -------- | -------------------------------------------------- | ------- |
| success  | Whether or not the room dynamic rates were removed | boolean |
