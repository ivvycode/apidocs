# Get Cost Center List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getCostCenterList" method="post" summary="Venue Cost Center List" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 50,
        "count": 1
    },
    "results": [
        {
            "id": 1,
            "name": "Food",
            "code": "venueccfd",
            "description": "Venue food cost center",
            "parentId": 321,
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties. The venueId is required, for example {"venuId":10}

## Returns

| Property    | Description                                             |
| ----------- | ------------------------------------------------------- |
| id          | The unique identifier of the cost center                |
| name        | The name of the cost center                             |
| code        | The code of the cost center                             |
| description | The complete description of the cost center             |
| parentId    | The unique identifier of the parent account cost center |

## Throws

| Code                 | Description            |
| -------------------- | ---------------------- |
| Specific Code: 24270 | Account does not exist |
| Specific Code: 24271 | Venue does not exist   |
