# Add or Update Rate Plan Booking Rules

## Description

Add or update the booking rules of venue rate plans.

NOTE: The dynamic data is only available to venues that integrate with a distribution channel.

## API URL

`[PlatformAddress]/api/1.0/venue?action=addOrUpdateRatePlanBookingRules`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| venueId | The unique id of the venue to which the rate plan belongs | Required | integer |
| barId | The unique id of the rate plan to which the booking rule applies | Required | integer |
| roomId | The unique id of the room to which the booking rule applies | Required | integer |
| startDate | The start date from which the booking rule will apply | Required | date |
| endDate | The end date until which the booking rule will apply | Required | date |
| closeOutStatus | The close out status of the booking rule from startDate to endDate | Required | [CloseOutStatus](add-or-update-rateplan-bookingrules.md#close-out-status) |

## Returns

| Property | Description | Type |
| --- | --- | --- |
| success | Whether or not the rate plan booking rules were updated | boolean |

## Examples

### Setting the rate plan booking rules for a single date

**REQUEST**

```javascript
{
  "venueId": 123,
  "barId": 456,
  "roomId": 789,
  "startDate": "2018-07-27",
  "endDate": "2018-07-27",
  "closeOutStatus": 2  
}
```

**RESPONSE**

```javascript
{
  "success": true
}
```

### Setting the rate plan booking rules for a date range

**REQUEST**

```javascript
{
  "venueId": 123,
  "barId": 456,
  "roomId": 789,
  "startDate": "2018-07-27",
  "endDate": "2018-08-03",
  "closeOutStatus": 2  
}
```

**RESPONSE**

```javascript
{
  "success": true
}
```

## Close Out Status

The following close out status values are supported by the current booking rules.

\| 1 \| The room is open for bookings \| \| 2 \| The room is closed for bookings \|

