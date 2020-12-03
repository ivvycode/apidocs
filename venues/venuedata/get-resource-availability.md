# Get Resource Availability

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getResourceAvailability" path="" %}
{% api-method-summary %}
Get Resource Availability
{% endapi-method-summary %}

{% api-method-description %}
Return the availability for resources.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="date" required=true %}
The start date of the period from which to include the resource availability details.
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="date" required=true %}
The end date of the period from which to include the resource availability details.
{% endapi-method-parameter %}

{% api-method-parameter name="resourceIds" type="array" required=true %}
The end date of the period from which to include the resource availability details.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 100,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "unAvailableTimes": [
                {
                    "startDate": "2018-01-17 08:00:00",
                    "endDate": "2018-01-17 09:00:00"
                }
            ]
        },
        {
            "id": 24,
            "unAvailableTimes": []
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get Resource Availability`

```javascript
{
    "venueId": 1,
    "startDate": "2018-01-10 00:00:00",
    "endDate": "2018-01-18 23:59:00",
    "resourceIds": [1, 24]
}
```

## Returns

`A collection object with the following properties in the results`

| Property | Description |
| :--- | :--- |
| id | The unique resource identifier |
| unAvailableTimes | The unavailable date time ranges |

