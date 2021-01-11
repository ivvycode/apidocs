# Add or Update Room Counts

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateRoomCountsCollection" path="" %}
{% api-method-summary %}
Add or Update Room Counts
{% endapi-method-summary %}

{% api-method-description %}
Add or update the dynamic inventory counts of venue rooms
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the room belongs
{% endapi-method-parameter %}

{% api-method-parameter name="items" type="array" required=true %}
The array of items. See Item table below for individual item data.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

| Property | Description | Type |
| :--- | :--- | :--- |
| success | Whether or not the room inventory counts were updated | boolean |

## Item Details

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| roomId | integer | required | The unique id of the room for which the inventory count will be set |
| startDate | date | required | The start date from which the room inventory count will be set \(Date Format\) |
| endDate | date | required | The end date from which the room inventory count will be set \(Date Format\) |
| roomCount | integer | required | The inventory count of the room from startDate to endDate |

