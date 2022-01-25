# Get Resource Availability

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getResourceAvailability" method="post" summary="Get Resource Availability" %}
{% swagger-description %}
Return the availability for resources.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="startDate" type="date" in="path" %}
The start date of the period from which to include the resource availability details.
{% endswagger-parameter %}

{% swagger-parameter name="endDate" type="date" in="path" %}
The end date of the period from which to include the resource availability details.
{% endswagger-parameter %}

{% swagger-parameter name="resourceIds" type="array" in="path" %}
The end date of the period from which to include the resource availability details.
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
{% endswagger-response %}
{% endswagger %}

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

| Property         | Description                      |
| ---------------- | -------------------------------- |
| id               | The unique resource identifier   |
| unAvailableTimes | The unavailable date time ranges |
