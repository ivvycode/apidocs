# Add or Update Event

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/event?action=addOrUpdateEvent" %}
{% api-method-summary %}
addOrUpdateEvent
{% endapi-method-summary %}

{% api-method-description %}
Add or update event details.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="eventType" type="string" required=true %}
Required when adding an event. Value must be 12. The value cannot be changed for an existing event. 
{% endapi-method-parameter %}

{% api-method-parameter name="title" type="string" required=true %}
Required when adding an event. The title of the event. Max Length: 140
{% endapi-method-parameter %}

{% api-method-parameter name="timezone" type="string" required=true %}
Required when adding an event. The timezone of the event. \(Datatype = timestamp\)
{% endapi-method-parameter %}

{% api-method-parameter name="startDateTime" type="string" required=true %}
When adding an event. The start date & time of the event.
{% endapi-method-parameter %}

{% api-method-parameter name="endDateTime" type="string" required=true %}
When adding an event. The end date & time of the event. The value must be on or after startDateTime. \(Datatype = timestamp\)
{% endapi-method-parameter %}

{% api-method-parameter name="capacity" type="integer" required=false %}
The maximum number of attendees who can register for the event. A value of 0 \(zero\) represents no limit.
{% endapi-method-parameter %}

{% api-method-parameter name="budget" type="number" required=false %}
A budget amount assigned to the event. \(Datatype = float\)
{% endapi-method-parameter %}

{% api-method-parameter name="costCenterId" type="integer" required=false %}
A cost center assigned to the event. The value is an identifier of a cost center in the account, which must be assignable to events.
{% endapi-method-parameter %}

{% api-method-parameter name="primaryContactUserId" type="integer" required=false %}
The primary contact user of the event. The value is an identifier of a user in the account.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "success": true,
  "id": 98481,
  "code": "BAS4G248"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The event’s unique identifier. Exclude to add an event. Include to update an existing event. | Required | integer |
| eventType | The type of event. Value must be 12 \(Record Event Details\). The value cannot be changed for an existing event. | Required | integer |
| code | The event’s unique code. Can be excluded when adding an event \(system will assign a unique code\). The value cannot be changed for an existing event. |  | string |
| title | Required: when adding an event. The title of the event. |  | string |
| timezone | Required: when adding an event. The timezone of the event. |  | timezone |
| startDateTime | Required: when adding an event. The start date & time of the event. |  | timestamp |
| endDateTime | Required: when adding an event. The end date & time of the event. The value must be on or after startDateTime. |  | timestamp |
| capacity | The maximum number of attendees who can register for the event. A value of 0 \(zero\) represents no limit. |  | integer |
| budget | A budget amount assigned to the event. |  | float |
| costCenterId | A cost center assigned to the event. The value is an identifier of a cost center in the account, which must be assignable to events. |  | integer |
| primaryContactUserId | The primary contact user of the event. The value is an identifier of a user in the account. |  | integer |

This action call accepts the parameters of an event and will;

1\) Add a new event to the account

2\) Update an existing event in the account when the id parameter is provided.

NOTE: This action call only supports “Record Event Details” type events \(i.e. eventType value of 12\).

## Returns

| Property | Description | Type |
| --- | --- | --- |
| success | Whether or not the action succeeded \(i.e. the event as added or updated\). | boolean |
| id | The event’s unique identifier. The value will be null on failure. | integer |
| code | The event’s unique code. The value will be null on failure. | string |

