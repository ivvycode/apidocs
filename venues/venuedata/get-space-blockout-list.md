# Get Space Blockout List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getSpaceBlockoutList" method="post" summary="Get Venue Space Blockout List" %}
{% swagger-description %}
Return the venue space blockout list for the venue.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 56,
        "start": 0,
        "perPage": 2,
        "count": 2
    },
    "results": [
        {
            "id": 2,
            "venueId": 1,
            "spaceId": 5,
            "name": "Public Holiday 1",
            "startDate": "2022-01-17",
            "startTime": "12:00:00",
            "endDate": "2022-01-17",
            "endTime": "13:00:00",
            "bookedById": 1
        },
        {
            "id": 3,
            "venueId": 1,
            "spaceId": 4,
            "name": "Booked by XYZ",
            "startDate": "2022-01-17",
            "startTime": "05:00:00",
            "endDate": "2022-01-17",
            "endTime": "06:00:00",
            "bookedById": 1
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Space Blockout List`

```javascript
{
  "venueId": 1
}
```

## Returns

`A collection object with the following properties in the results`

| Property                    | Data Type | Description                                                                                                                                                                                                                              |
| --------------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                          | integer   | The unique identifier of the space blockout.                                                                                                                                                                                                              |
| venueId                     | integer   |The unique id of the venue to which the space blockout belongs.                                                                                                                                                                                          |
| spaceId                     | integer   |he unique id of the function space to which the space blockout belongs.                                                                                                                                                                                          |
| name                        | string    | The name of the space blockout.                                                                                                                                                                                                                   |
| startDate                 | date    | The start date of the space blockout.                                                                                                                                                                                                            |
| startTime                  | time   | The start time of the space blockout.                                                                                                                                                                                            |
| endDate                     | date   | The end date of the space blockout.                                                                                                                                                                                                      |
| endTime                  | time   | The end time of the space blockout.                                                                                                                                                                                                    |
| bookedById                      | integer   | 'The coordinator user who created the space blockout.