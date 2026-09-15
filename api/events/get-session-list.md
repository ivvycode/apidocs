# Get Speaker List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="event?action=getSessionList" method="post" summary="Get Session List" %}
{% swagger-description %}
Get the list of sessions at an event
{% endswagger-description %}

{% swagger-parameter name="eventId" type="integer" in="path" %}
The event identifier
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 100,
        "count": 1
    },
    "results": [
        {
            "id": 1,
            "eventId": 1,
            "name": "Test Session 1",
            "startDate": "2018-04-18 03:30:00 UTC",
            "endDate": "2018-04-18 15:00:00 UTC",
            "description": null,
            "roomId": 1,
            "isOptional": true,
            "maxCapacity": 10,
            "costAmount": 100,
            "isTaxFree": true,
            "autoCloseDate": "2025-03-12 19:30:00 UTC",
            "setupTime": 3,
            "breakdownTime": 4,
            "speakers": [
                1,
                2581
            ],
            "showInAgenda": true,
            "showTime": true,
            "onlyForCertainTickets": true,
            "tickets": [
                1,
                576
            ],
            "notes": "Session notes",
            "setupNotes": "setup notes",
            "createdDate": "2018-04-19 05:51:17 UTC",
            "modifiedDate": "2025-03-11 23:17:05 UTC",
            "allowGuests": true
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Example: Fetch the list of sessions at an event`

```javascript
{
  "eventId":1
}
```

## Returns

A collection object with the following properties of objects in the results

| Property           | Description                            |
| ------------------ | -------------------------------------- |
| id                 | The unique identifier of the event session |
| eventId            | The unique identifier of the event to which the event session belong |
| name               | Session name |
| startDate          | The session start date & time |
| endDate            | The session end date & time |
| description        | The session HTML description |
| roomId             | The unique identifier of the room to which the event session belong |
| isOptional         | Whether or not the session is optional |
| maxCapacity        | Maximum # of attendees who can register for the session |
| costAmount         | Optional session cost |
| isTaxFree          | Whether or not the session tax to be applied |
| autoCloseDate      | The session auto close date |
| setupTime          | The setup time of the session (in minutes) |
| breakdownTime      | The breakdown time of the session (in minutes) |
| speakers           | Array of a unique identifier of the speakers to which the event session belong |
| showInAgenda       | Whether or not to show the session in the agenda |
| showTime           | Whether or not to show the time of the session |
| onlyForCertainTickets | Whether or not the session is available for certain tickets only |
| tickets            | The specific tickets that are available for this session (when onlyForCertainTickets = true) |
| notes              | Any notes for the session |
| setupNotes         | Setup notes |
| createdDate        | The session creation date & time |
| modifiedDate       | The session last modified date & time |
| allowGuests        | Whether or not guests are allowed to register for this session |

## Throws

| Code                 | Description                  |
| -------------------- | ---------------------------- |
| Specific Code: 24456 | Event does not exist         |
