# Get Function Space Availability

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getFunctionSpaceAvailability" path="" %}
{% api-method-summary %}
Get Venue Function Space Availability
{% endapi-method-summary %}

{% api-method-description %}
Returns the availability of function spaces in a specific venue.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="date" required=true %}
The date from which the availability data will be fetched. Format YYY-MM-DD
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="date" required=true %}
The date to which the availability data will be fetched. Format YYY-MM-DD. The maximum number of days of available that can be fetched is 14.
{% endapi-method-parameter %}

{% api-method-parameter name="spaceIds" type="array" required=false %}
Optionally the list of space ids to which availability will be limited.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

| Property | Data Type | Description |
| :--- | :--- | :--- |
| availability | array | Array of spaces with availability data. See "Space Availability" for details. |

## Space Availability

`A collection object with the following properties in the results`

| Property | Data Type | Description |
| :--- | :--- | :--- |
| spaceId | integer | The id of space to which the time slots belong. |
| timeSlots | array | The array of time slots. See "Space Time Slots" for details. |

## Space Time Slots

`A collection object with the following properties in the results`

| Property | Data Type | Description |
| :--- | :--- | :--- |
| date | date | The date to which the time slot applies. Format YYYY-MM-DD |
| startTime | string | The start time of the available time slot. Format H:i:s |
| endTime | string | The end time of the available time slot. Format H:i:s |

