# Add or Update Event

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="event?action=addOrUpdateEvent" method="post" summary="addOrUpdateEvent" %}
{% swagger-description %}
Add or update event details.
{% endswagger-description %}

{% swagger-parameter name="businessUnitId" type="integer" in="body" %}
Required when business unit defined in event's account
{% endswagger-parameter %}

{% swagger-parameter name="eventType" type="string" in="body" %}
Required when adding an event. Value must be 12. The value cannot be changed for an existing event.
{% endswagger-parameter %}

{% swagger-parameter name="title" type="string" in="body" %}
Required when adding an event. The title of the event. Max Length: 140
{% endswagger-parameter %}

{% swagger-parameter name="timezone" type="string" in="body" %}
Required when adding an event. The timezone of the event. (Datatype = timestamp)
{% endswagger-parameter %}

{% swagger-parameter name="startDateTime" type="string" in="body" %}
When adding an event. The start date & time of the event.
{% endswagger-parameter %}

{% swagger-parameter name="endDateTime" type="string" in="body" %}
When adding an event. The end date & time of the event. The value must be on or after startDateTime. (Datatype = timestamp)
{% endswagger-parameter %}

{% swagger-parameter name="capacity" type="integer" in="body" %}
The maximum number of attendees who can register for the event. A value of 0 (zero) represents no limit.
{% endswagger-parameter %}

{% swagger-parameter name="budget" type="number" in="body" %}
A budget amount assigned to the event. (Datatype = float)
{% endswagger-parameter %}

{% swagger-parameter name="costCenterId" type="integer" in="body" %}
A cost center assigned to the event. The value is an identifier of a cost center in the account, which must be assignable to events.
{% endswagger-parameter %}

{% swagger-parameter name="primaryContactUserId" type="integer" in="body" %}
The primary contact user of the event. The value is an identifier of a user in the account.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true,
  "id": 98481,
  "code": "BAS4G248"
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

```javascript
{
  "eventType": 12,
  "title": "A New Event",
  "timezone": "Australia/Sydney",
  "startDateTime": "2018-03-05 03:00:00 UTC",
  "endDateTime": "2018-03-05 06:00:00 UTC",
  "capacity": 10,
  "budget": 150,
  "costCenterId": 834,
  "primaryContactUserId": 7821,
  "eventTypeIds": [56,57],
  "isAccommIncluded": false
}
```

This action call accepts the parameters of an event and will;

1\) Add a new event to the account

2\) Update an existing event in the account when the id parameter is provided.

NOTE: This action call only supports “Record Event Details” type events (i.e. eventType value of 12).

## Returns

| Property | Description                                                               | Type    |
| -------- | ------------------------------------------------------------------------- | ------- |
| success  | Whether or not the action succeeded (i.e. the event as added or updated). | boolean |
| id       | The event’s unique identifier. The value will be null on failure.         | integer |
| code     | The event’s unique code. The value will be null on failure.               | string  |
