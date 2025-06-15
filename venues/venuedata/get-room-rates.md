# Get Room Rates

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getRoomRates" method="post" summary="Get Room Rates" %}
{% swagger-description %}
Return the room rates for the given rate plan and date and optionally provided room ids.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" required="true" %}
The unique id of the venue to which the room belongs.
{% endswagger-parameter %}

{% swagger-parameter name="barId" type="integer" in="body" required="true" %}
The unique id of the rate plan.
{% endswagger-parameter %}

{% swagger-parameter name="startDate" type="date" in="body" required="true" %}
The start date of the rate.
{% endswagger-parameter %}

{% swagger-parameter name="endDate" type="date" in="body" required="true" %}
The end date of the rate.
{% endswagger-parameter %}

{% swagger-parameter name="roomIds" type="array" in="body" required="false" %}
The room ids to filter the rates.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
{
    "meta": {
        "totalResults": 4,
        "start": 0,
        "perPage": 4,
        "count": 4
    },
    "results": [
        {
            "barId": 63,
            "roomId": 122,
            "date": "2025-07-06",
            "minAcceptableRate": null,
            "cost": null,
            "costDouble": null,
            "costTriple": null,
            "costQuad": null
        },
        {
            "barId": 63,
            "roomId": 123,
            "date": "2025-07-06",
            "minAcceptableRate": 100,
            "cost": 50,
            "costDouble": 60,
            "costTriple": 0,
            "costQuad": 80
        },
        {
            "barId": 63,
            "roomId": 122,
            "date": "2025-07-07",
            "minAcceptableRate": null,
            "cost": null,
            "costDouble": null,
            "costTriple": null,
            "costQuad": null
        },
        {
            "barId": 63,
            "roomId": 123,
            "date": "2025-07-07",
            "minAcceptableRate": 200,
            "cost": 5,
            "costDouble": 6,
            "costTriple": 7,
            "costQuad": 0
        }
    ]
}

```
{% endswagger-response %}

# Example Request
```json
{
    "venueId": 447,
    "startDate": "2025-07-06",
    "endDate": "2025-07-07",
    "barId": 63,
    "roomIds": [122, 123]
}
```
{% endswagger %}

# Date Range Restrictions

- **startDate and endDate**: The maximum date range is 31 days. Past dates are not allowed.

# Returns

A collection object with the following properties in result

| Property           | Data Type | Description                                                 |
|--------------------|-----------|-------------------------------------------------------------|
| barId              | integer   | The unique id of the rate plan                              |
| date               | date    | The date of the inventory                                   |
| roomId             | integer   | The unique id of the room                                   |
| minAcceptableRate  | float     | The minimum acceptable rate for the room on the given date  |
| cost               | float     | The cost of the room for a given day for single occupancy   |
| costDouble         | float     | The cost of the room for a given day for two occupants      |
| costTriple         | float     | The cost of the room for a given day for three occupants    |
| costQuad           | float     | The cost of the room for a given day for four occupants     |
