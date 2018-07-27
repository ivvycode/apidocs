# Add or Update Room Counts

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateRoomCounts" path="" %}
{% api-method-summary %}
Add or Update Room Counts
{% endapi-method-summary %}

{% api-method-description %}
Add or update the dynamic inventory counts of venue rooms
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the room belongs
{% endapi-method-parameter %}

{% api-method-parameter name="roomId" type="integer" required=true %}
The unique id of the room for which the inventory count will be set
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="string" required=true %}
The start date from which the room inventory count will be set \(Date Format\)
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="string" required=true %}
The end date from which the room inventory count will be set \(Date Format\)
{% endapi-method-parameter %}

{% api-method-parameter name="roomCount" type="integer" required=true %}
The inventory count of the room from startDate to endDate
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

### Setting the room count for a single date

```javascript
{
  "venueId": 123,
  "roomId": 456,
  "startDate": "2018-07-27",
  "endDate": "2018-07-27",
  "roomCount": 9
}
```

### Setting the room count for a date range

```javascript
{
  "venueId": 123,
  "roomId": 456,
  "startDate": "2018-07-27",
  "endDate": "2018-08-03",
  "roomCount": 10
}
```

## Returns

| Property | Description | Type |
| --- | --- | --- |
| success | Whether or not the room inventory counts were updated | boolean |

