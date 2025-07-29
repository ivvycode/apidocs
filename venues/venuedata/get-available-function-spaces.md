# Get Available Function Spaces

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getAvailableFunctionSpaces" method="post" summary="Get Venue Function Space Availability" %}
{% swagger-description %}
Returns the availability of function spaces in a specific venue based on some filtering criteria. This API is different to [Get Function Space Availability](get-function-space-availability.md) in that besides allowing extra filtering, it returns the availability of function spaces for a maximum date-time range of 24 hours only. Availability timeslots are not returned.

{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="startDatetime" type="timestamp" in="path" %}
The start date and time of the activity. Format is Y-m-d H:i:s
{% endswagger-parameter %}

{% swagger-parameter name="endDatetime" type="timestamp" in="path" %}
The end date and time of the activity. Format is Y-m-d H:i:s. The date and time range that of availability that can be fetched is 24 hours.
{% endswagger-parameter %}

{% swagger-parameter name="eventType" type="integer" in="path" %}
The event type id applied to the function space
{% endswagger-parameter %}

{% swagger-parameter name="pax" type="integer" in="path" %}
The number of attendees that the function space will be used for
{% endswagger-parameter %}

{% swagger-parameter name="layoutType" type="integer" in="path" %}
The layout type of the function space
{% endswagger-parameter %}

{% swagger-parameter name="spaceIds" type="array" in="path" %}
Optionally the list of space ids to which availability will be limited.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}

```
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 100,
        "count": 2
    },
    "results": [
        {
            "id": 5991,
            "name": "Main Hall",
            "isAvailable": true,
            "reason": null,
            "conflict": null
        },
        {
            "id": 6048,
            "name": "Music hall",
            "isAvailable": false,
            "reason": null,
            "conflict": {
                "venueId": 1,
                "bookingId": 30167,
                "sessionId": 25728,
                "spaceId": 6048,
                "startDate": "2025-07-20 09:00:00",
                "endDate": "2025-07-20 10:00:00",
                "pax": 10
            }
        }
    ]
}
```

{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Available function spaces`

```javascript
{
    "venueId":1,
    "startDatetime": "2025-11-26 09:00:00",
    "endDatetime": "2025-11-26 10:00:00",
    "eventType": 1,
    "pax": 10,
    "layoutType": 1,
    "spaceIds": [1]
}
```

## Returns

| Property    | Data Type | Description                                                            |
| ----------- | --------- | ---------------------------------------------------------------------- |
| id          | integer   | The id of space to which the time slots belong.                        |
| name        | string    | The name of space                                                      |
| isAvailable | boolean   | Whether the space is available                                         |
| reason      | integer   | 1 - The reserviation is unavailable because the space has been blocked |
| conflict    | object    | The conflict object                                                    |

## Conflict

| Property  | Data Type | Description                                                      |
| --------- | --------- | ---------------------------------------------------------------- |
| venueId   | integer   | The id of venue                                                  |
| bookingId | integer   | The id of booking                                                |
| sessionId | integer   | The id of session                                                |
| spaceId   | integer   | The id of space                                                  |
| startDate | string    | The start date of the conflict                                   |
| endDate   | string    | The end date of the conflict                                     |
| pax       | integer   | The number of attendees that the function space will be used for |

## Conflict Reason

| Value | Description                                                                  |
| ----- | ---------------------------------------------------------------------------- |
| 1     | The reservation is unavailable because the space has been blocked            |
| 2     | The reservation is unavailable because the max pax on space has been crossed |
