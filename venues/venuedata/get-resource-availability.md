# Get Resource Availability

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getResourceAvailability" method="post" summary="Get Resource Availability" %}
{% swagger-description %}
Return the availability for resources.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" required=true in="body" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="startDate" type="date" required=true in="body" %}
The start date of the period from which to include the resource availability details.
{% endswagger-parameter %}

{% swagger-parameter name="endDate" type="date" required=true in="body" %}
The end date of the period from which to include the resource availability details.
{% endswagger-parameter %}

{% swagger-parameter name="resourceIds" type="array"  required=truein="body" %}
The end date of the period from which to include the resource availability details.
{% endswagger-parameter %}

{% swagger-parameter name="quantity" type="integer" required=false in="body" %}
Specifies the quantity to check for resource availability.
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
                    "startDate": "2021-06-24 00:00:00",
                    "endDate": "2021-06-24 23:59:00",
                    "quantity": 10
                }
            ],
            "isAvailable": true,
            "conflict": null
        },
        {
            "id": 25,
            "unAvailableTimes": [
                {
                    "startDate": "2021-06-24 00:00:00",
                    "endDate": "2021-06-24 23:59:00",
                    "quantity": 10
                }
            ],
            "isAvailable": false,
            "conflict": {
                "venueId": 1,
                "bookingId": 20815,
                "sessionId": 11544,
                "spaceId": 288,
                "resourceId": 25,
                "startDate": "2021-06-24 00:00:00",
                "endDate": "2021-06-24 23:59:00",
                "quantity": 10
            }
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
    "startDate": "2021-06-24 00:00:00",
    "endDate": "2021-06-25 00:00:00",
    "resourceIds": [1, 25],
    "quantity": 10
}
```

## Returns

`A collection object with the following properties in the results`

| Property         | Description                                            |
| ---------------- | ------------------------------------------------------ |
| id               | The unique resource identifier                         |
| unAvailableTimes | The reserved date time ranges for resource with quantity            |
| isAvailble       | Whether or not resource is available for given time range and quantity. (Only when request contains quantity)
| conflict         | If resource is not available (i.e. isAvailable to false), then it gives conflicted session details (Only when request contains quantity) |
