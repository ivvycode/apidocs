# Get Function Space Availability

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getFunctionSpaceAvailability" method="post" summary="Get Venue Function Space Availability" %}
{% swagger-description %}
Returns the availability of function spaces in a specific venue.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="startDate" type="date" in="path" %}
The date from which the availability data will be fetched. Format YYY-MM-DD
{% endswagger-parameter %}

{% swagger-parameter name="endDate" type="date" in="path" %}
The date to which the availability data will be fetched. Format YYY-MM-DD. The maximum number of days of available that can be fetched is 14.
{% endswagger-parameter %}

{% swagger-parameter name="spaceIds" type="array" in="path" %}
Optionally the list of space ids to which availability will be limited.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "availability": [
        {
            "spaceId": 1,
            "timeSlots": [
                {
                    "date": "2020-11-26",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                },
                {
                    "date": "2020-11-27",
                    "startTime": "00:00:00",
                    "endTime": "09:00:00"
                },
                {
                    "date": "2020-11-27",
                    "startTime": "17:00:00",
                    "endTime": "23:59:59"
                },
                {
                    "date": "2020-11-28",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                },
                {
                    "date": "2020-11-29",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                },
                {
                    "date": "2020-11-30",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                }
            ]
        },
        {
            "spaceId": 2,
            "timeSlots": [
                {
                    "date": "2020-11-26",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                },
                {
                    "date": "2020-11-27",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                },
                {
                    "date": "2020-11-28",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                },
                {
                    "date": "2020-11-29",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                },
                {
                    "date": "2020-11-30",
                    "startTime": "00:00:00",
                    "endTime": "23:59:59"
                }
            ]
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Venues Function Space List`

```javascript
{
    "venueId":1,
    "startDate": "2020-11-26",
    "endDate": "2020-11-30",
    "spaceIds": [1, 2]
}
```

## Returns

`A collection object with the following properties in the results`

| Property     | Data Type | Description                                                                   |
| ------------ | --------- | ----------------------------------------------------------------------------- |
| availability | array     | Array of spaces with availability data. See "Space Availability" for details. |

## Space Availability

`A collection object with the following properties in the results`

| Property  | Data Type | Description                                                  |
| --------- | --------- | ------------------------------------------------------------ |
| spaceId   | integer   | The id of space to which the time slots belong.              |
| timeSlots | array     | The array of time slots. See "Space Time Slots" for details. |

## Space Time Slots

`A collection object with the following properties in the results`

| Property  | Data Type | Description                                                |
| --------- | --------- | ---------------------------------------------------------- |
| date      | date      | The date to which the time slot applies. Format YYYY-MM-DD |
| startTime | string    | The start time of the available time slot. Format H:i:s    |
| endTime   | string    | The end time of the available time slot. Format H:i:s      |
