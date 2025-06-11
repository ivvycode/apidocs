# Get Rate Plan Booking Rules

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getRatePlanBookingRules" method="post" summary="Get Rate Plan Booking Rules" %}
{% swagger-description %}
Return the rate plan booking rules for the given date and optionally room ids.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" required="true" %}
The unique id of the venue to which the room belongs.
{% endswagger-parameter %}

{% swagger-parameter name="startDate" type="string" in="body" required="true" %}
The start date of the rate plan rule which it applies to.
{% endswagger-parameter %}

{% swagger-parameter name="endDate" type="string" in="body" required="true" %}
The end date of the rate plan rule which it applies to.
{% endswagger-parameter %}

{% swagger-parameter name="roomIds" type="array" in="body" required="false" %}
The room ids to filter the rate plan rule.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
{
    "meta": {
        "totalResults": 3,
        "start": 0,
        "perPage": 3,
        "count": 3
    },
    "results": [
        {
            "barId": 1,
            "roomId": 6,
            "date": "2026-05-09",
            "closeOutStatus": 2
        },
        {
            "barId": 1,
            "roomId": 6,
            "date": "2026-05-10",
            "closeOutStatus": 2
        },
        {
            "barId": 1,
            "roomId": 6,
            "date": "2026-05-11",
            "closeOutStatus": null
        }
    ]
}

```
{% endswagger-response %}

# Example Request
```json
{
    "venueId": 1,
    "startDate": "2026-05-09",
    "endDate": "2026-05-11",
    "barId": 1,
    "roomIds": [6]
}
```
{% endswagger %}

# Date Range Restrictions

- **startDate and endDate**: The maximum date range is 31 days. Past dates are not allowed.

# Returns

A collection object with the following properties in result

| Property        | Data Type | Description                              |
|-----------------|-----------|------------------------------------------|
| barId           | string    | The unique id of the rate plan                |
| date            | string    | The date of the rate plan rule which it applies to                |
| roomId          | integer   | The unique id of the room                |
| closeOutStatus  | integer   | The close out status of the rate plan rule on the given date                          |
