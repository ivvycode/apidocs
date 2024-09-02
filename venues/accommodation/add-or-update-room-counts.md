# Add or Update Room Counts

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=addOrUpdateRoomCountsCollection" method="post" summary="Add or Update Room Counts" %}
{% swagger-description %}
Add or update the dynamic inventory counts of venue rooms
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the room belongs
{% endswagger-parameter %}

{% swagger-parameter name="items" type="array" in="path" %}
The array of items. See Item table below for individual item data.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true
}
```
{% endswagger-response %}
{% endswagger %}

NOTE: The dynamic data is only available to venues that integrate with a distribution channel.

## Examples

### Setting the room count for a single date

```javascript
{
    "venueId": 1,
    "items": [
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-01",
            "roomId": 2,
            "roomCount": 11
        }
    ]
}
```

### Setting the room count for a date range

```javascript
{
    "venueId": 1,
    "items": [
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-10",
            "roomId": 2,
            "roomCount": 11
        },
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-10",
            "roomId": 3,
            "roomCount": 21
        },
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-10",
            "roomId": 4,
            "roomCount": 16
        },
        {
            "startDate": "2020-05-11",
            "endDate": "2020-05-20",
            "roomId": 2,
            "roomCount": 11
        },
        {
            "startDate": "2020-05-11",
            "endDate": "2020-05-20",
            "roomId": 3,
            "roomCount": 21
        },
        {
            "startDate": "2020-05-11",
            "endDate": "2020-05-20",
            "roomId": 4,
            "roomCount": 16
        }
    ]
}
```

## Returns

| Property | Description                                           | Type    |
| -------- | ----------------------------------------------------- | ------- |
| success  | Whether or not the room inventory counts were updated | boolean |

## Item Details

| Property  | Type    | Required | Description                                                                  |
| --------- | ------- | -------- | ---------------------------------------------------------------------------- |
| roomId    | integer | required | The unique id of the room for which the inventory count will be set          |
| startDate | date    | required | The start date from which the room inventory count will be set (Date Format) |
| endDate   | date    | required | The end date from which the room inventory count will be set (Date Format)   |
| roomCount | integer | required | The inventory count of the room from startDate to endDate                    |
