# Get Booking List

### Description

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

### API URL

`[PlatformAddress]/api/1.0/venue?action=getBookingList`

### Example Request

`Get a specific venue’s Booking List`

```javascript
{
  "venueId": "1",
  "perPage": 1
}
```

### Example Response

```javascript
{
  "meta": {
    "totalResults": 256,
    "start": 0,
    "perPage": 1,
    "count": 1
  },
  "results": [
    {
      "id": 1,
      "venueId": 1,
      "code": "HR5ZASGMQ1",
      "name": "Some Booking",
      "eventType": "Holiday",
      "company": {
        "id": 4,
        "businessName": "Some Business"
      },
      "contact": {
        "id": 3,
        "firstName": "Quamar",
        "lastName": "Boyer",
        "email": "faly@gmail.com",
        "phone": "+247-92-9848064"
      },
      "currentStatus": 3,
      "totalAmount": 105,
      "totalTaxAmount": 5,
      "amountOutstanding": -425.3,
      "accountTimezone": null,
      "venueTimezone": null,
      "createdDate": "2015-01-07 09:21:53 UTC",
      "modifiedDate": "2016-04-06 07:51:56 UTC",
      "dateEventStart": "2015-06-01 00:00:00 UTC",
      "dateEventEnd": "2015-06-04 00:00:00 UTC",
      "isAccommIncluded": true,
      "dateAccomStart": "2015-06-01 00:00:00 UTC",
      "dateAccomEnd": "2015-06-27 00:00:00 UTC",
      "hasPackages": true,
      "decisionDate": "",
      "isBeoFinalised": true,
      "beoFinalisedDate": "2015-02-09 03:37:39 UTC"
    }
  ]
}
```

### currentStatus:

One of the following values:

* 1 = Prospective
* 2 = Tentative
* 3 = Confirmed
* 4 = Cancelled
* 5 = Ordering
* 8 = Not Accepted

### Additional Parameters

| Property | Description | Type |
| --- | --- | --- |
| modifiedDateBefore | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| modifiedDateAfter | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |

### Additional [Filter](../interpreting-the-response/filtering.md) Properties

| Property | Description | Type |
| --- | --- | --- |
| companyId | Filter by unique id of company | integer |
| contactId | Filter by unique id of contact | integer |

