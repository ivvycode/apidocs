# Get Booking

### Description

The result from this call will be the details of a specific booking to which the user has access. The unique venue identifier is required, for example {“id”:123}

### API URL

`[PlatformAddress]/api/1.0/venue?action=getBooking`

### Example Request

`Get a specific Booking`

```javascript
{
  "id": 3
}
```

### Example Response

```javascript
{
  "id": 3,
  "venueId": 1,
  "code": "123a",
  "name": "Ava Donovan",
  "eventType": "Holiday",
  "company": null,
  "contact": null,
  "currentStatus": 3,
  "totalAmount": 2600,
  "totalTaxAmount": 0,
  "amountOutstanding": 2600,
  "accountTimezone": "Australia/Brisbane",
  "venueTimezone": "Australia/Brisbane",
  "createdDate": "2015-01-21 09:50:49 UTC",
  "modifiedDate": "2016-04-06 07:51:56 UTC",
  "dateEventStart": "1996-02-19 00:00:00 UTC",
  "dateEventEnd": "2002-11-06 00:00:00 UTC",
  "isAccommIncluded": false,
  "dateAccomStart": "",
  "dateAccomEnd": "",
  "hasPackages": true,
  "decisionDate": "",
  "isBeoFinalised": false,
  "beoFinalisedDate": "",
  "dailyRevenue": [
    {
      "costcenterId": 1276,
      "revenueDate": "2015-09-04",
      "totalAmount": 2500,
      "totalTaxAmount": 227.273
    },
    {
      "costcenterId": 1277,
      "revenueDate": "2015-09-04",
      "totalAmount": 2500,
      "totalTaxAmount": 227.273
    },
    {
      "costcenterId": 1278,
      "revenueDate": "2015-09-04",
      "totalAmount": 2500,
      "totalTaxAmount": 227.273
    },
    {
      "costcenterId": 1279,
      "revenueDate": "2015-09-04",
      "totalAmount": 2500,
      "totalTaxAmount": 227.273
    }
  ]
}
```

### currentStatus

One of the following values:

| \# | Description |
| --- | --- |
| 1 | Prospective |
| 2 | Tentative |
| 3 | Confirmed |
| 4 | Cancelled |
| 5 | Ordering |
| 8 | Not Accepted |

