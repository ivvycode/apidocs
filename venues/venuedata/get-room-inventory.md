# Get Room Inventory

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getRoomInventory" method="post" summary="Get Room Inventory" %}
{% swagger-description %}
Return the inventory and available count for the given date and optionally provided room ids.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" required="true" %}
The unique id of the venue to which the resource belongs.
{% endswagger-parameter %}

{% swagger-parameter name="startDate" type="date" in="body" required="true" %}
The start date of the inventory.
{% endswagger-parameter %}

{% swagger-parameter name="endDate" type="date" in="body" required="true" %}
The end date of the inventory.
{% endswagger-parameter %}

{% swagger-parameter name="roomIds" type="array" in="body" required="false" %}
The room ids to filter the inventory.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 2,
        "count": 2
    },
    "results": [
        {
            "date": "2025-12-16",
            "roomId": 7,
            "inventoryCount": 3,
            "availableCount": 3
        },
        {
            "date": "2025-12-16",
            "roomId": 2,
            "inventoryCount": 130,
            "availableCount": 130
        },
    ]
}

```
{% endswagger-response %}

# Example Request
```json
{
    "venueId": 1,
    "startDate": "2025-06-01",
    "endDate": "2025-06-30",
    "roomIds": [101, 102]
}
```
{% endswagger %}

# Date Range Restrictions

- **startDate and endDate**: The maximum date range is 30 days. Past dates are not allowed.

# Returns

A collection object with the following properties in result

| Property        | Data Type | Description                              |
|-----------------|-----------|------------------------------------------|
| date            | date    | The date of the inventory                |
| roomId          | integer   | The unique id of the room                |
| inventoryCount  | integer   | The total rooms                          |
| availableCount  | integer   | The total available rooms after bookings |
