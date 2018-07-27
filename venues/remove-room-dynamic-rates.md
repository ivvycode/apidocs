# Remove Room Dynamic Rates

## Description

Remove one or more dynamic rates from venue rooms.

NOTE: The dynamic data is only available to venues that integrate with a distribution channel.

## API URL

`[PlatformAddress]/api/1.0/venue?action=removeRoomDynamicRates`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| venueId | The unique id of the venue to which the rate plan belongs | Required | integer |
| barId | The unique id of the rate plan to which the dynamic rate applies | Required | integer |
| roomId | The unique id of the room to which the rate applies | Required | integer |
| startDate | The start date from which the dynamic rate will be removed | Required | date |
| endDate | The end date until which the dynamic rate will be removed | Required | date |

## Returns

| Property | Description | Type |
| --- | --- | --- |
| success | Whether or not the room dynamic rates were removed | boolean |

## Examples

### Remove the room dynamic rates from a single date

**REQUEST**

```javascript
{
  "venueId": 123
  "barId": 456
  "roomId": 789
  "startDate": "2018-07-27"
  "endDate": "2018-07-27"
}
```

**RESPONSE**

```javascript
{
  "success": true
}
```

### Remove the room dynamic rates from multiple dates

**REQUEST**

```javascript
{
  "venueId": 123
  "barId": 456
  "roomId": 789
  "startDate": "2018-07-27"
  "endDate": "2018-08-03"
}
```

**RESPONSE**

```javascript
{
  "success": true
}
```

