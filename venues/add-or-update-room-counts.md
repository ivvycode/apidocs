# Add or Update Room Counts

## Description
Add or update the dynamic inventory counts of venue rooms.

NOTE: The dynamic data is only available to venues that integrate with a distribution channel.

## API URL

`[PlatformAddress]/api/1.0/venue?action=addOrUpdateRoomCounts`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| venueId | The unique id of the venue to which the room belongs | Required | integer |
| roomId | The unique id of the room for which the inventory count will be set | Required | integer |
| startDate | The start date from which the room inventory count will be set | Required | date |
| endDate | The end date until which the room inventory count will be set | Required | date |
| roomCount | The inventory count of the room from startDate to endDate | Required | integer |

## Returns

| Property | Description | Type |
| --- | --- | --- |
| success | Whether or not the room inventory counts were updated. | boolean |

## Examples

### Setting the room count for a single date

**REQUEST**

```javascript
{
  "venueId": 123,
  "roomId": 456,
  "startDate": "2018-07-27",
  "endDate": "2018-07-27",
  "roomCount": 9
}
```

**RESPONSE**

```javascript
{
  "success": true
}
```

### Setting the room count for a date range

**REQUEST**

```javascript
{
  "venueId": 123,
  "roomId": 456,
  "startDate": "2018-07-27",
  "endDate": "2018-08-03",
  "roomCount": 10
}
```

**RESPONSE**

```javascript
{
  "success": true
}
```

