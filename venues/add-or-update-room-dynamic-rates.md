# Add or Update Room Dynamic Rates

## Description
Add or update the dynamic rates of venue rooms.

NOTE: The dynamic data is only available to venues that integrate with a distribution channel.

## API URL

`[PlatformAddress]/api/1.0/venue?action=addOrUpdateRoomDynamicRates`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| venueId | The unique id of the venue to which the rate plan belongs | Required | integer |
| barId | The unique id of the rate plan to which the dynamic rate applies | Required | integer |
| roomId | The unique id of the room to which the rate applies | Required | integer |
| startDate | The start date from which the dynamic rate will be set | Required | date |
| endDate | The end date until which the dynamic rate will be set | Required | date |
| cost | The rate amount from startDate to endDate. The amount must either include or exclude tax depending on how the venue has been configured | Required | number |

## Returns

| Property | Description | Type |
| --- | --- | --- |
| success | Whether or not the room dynamic rates were updated. | boolean |

## Examples

### Setting the room dynamic rate for a single date

**REQUEST**
```javascript
{
  "venueId": 123,
  "barId": 456,
  "roomId": 789,
  "startDate": "2018-07-27",
  "endDate": "2018-07-27",
  "cost": 240.00
}
```

**RESPONSE**
```javascript
{
  "success": true
}
```

### Setting the room dynamic rate for a date range

**REQUEST**
```javascript
{
  "venueId": 123,
  "barId": 456,
  "roomId": 789,
  "startDate": "2018-07-27",
  "endDate": "2018-08-03",
  "cost": 234.50
}
```

**RESPONSE**
```javascript
{
  "success": true
}
```