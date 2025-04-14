# Add or Update Rate Plan Booking Rules

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=addOrUpdateRatePlanBookingRulesCollection" method="post" summary="Add or Update Rate Plan Booking Rules" %}
{% swagger-description %}
Add or Update the booking rules of venue rate plans
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the rate plan belongs
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

### Setting the rate plan booking rules for a single date

**REQUEST**

```javascript
{
    "venueId": 1,
    "items": [
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-01",
            "roomId": 2,
            "barId": 1,
            "closeOutStatus": 1
        }
    ]
}
```

### Setting the rate plan booking rules for a date range

**REQUEST**

```javascript
{
    "venueId": 1,
    "items": [
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-10",
            "roomId": 2,
            "barId": 1,
            "closeOutStatus": 1
        },
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-10",
            "roomId": 2,
            "barId": 147,
            "closeOutStatus": 1
        },
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-10",
            "roomId": 3,
            "barId": 1,
            "closeOutStatus": 1
        },
        {
            "startDate": "2020-05-01",
            "endDate": "2020-05-10",
            "roomId": 3,
            "barId": 147,
            "closeOutStatus": 1
        }
    ]
}
```

## Returns

| Property | Description                                             | Type    |
| -------- | ------------------------------------------------------- | ------- |
| success  | Whether or not the rate plan booking rules were updated | boolean |

## Close Out Status

The following close out status values are supported by the current booking rules.

| Value | Description                     |
| ----- | ------------------------------- |
| 1     | The room is open for bookings   |
| 2     | The room is closed for bookings |

## Item Details

| Property       | Type    | Required | Description                                                                              |
| -------------- | ------- | -------- | ---------------------------------------------------------------------------------------- |
| barId          | integer | required | The unique id of the rate plan to which the booking rule applies                         |
| roomId         | integer | required | The unique id of the room to which the booking rule applies                              |
| startDate      | date    | required | The start date from which the booking rule will apply (Date Format)                      |
| endDate        | date    | required | The end date until which the booking rule will apply (Date Format)                       |
| closeOutStatus | integer | required | The close out status of the booking rule from startDate to endDate. 1 = Open, 2 = Closed |
