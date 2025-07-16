# Get Booking List For Account

## Get Booking List for Account

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/venue?action=getBookingListForAccount`

A collection of bookings for the account that the user has access (as opposed to bookings for a single venue in an account for get Bookings List)

#### Path Parameters

| Name    | Type    | Description                                    |
| ------- | ------- | ---------------------------------------------- |
| perPage | integer | The number of bookings to get in a single call |

{% tabs %}
{% tab title="200 " %}
```
{
  "meta": {
    "totalResults": 325,
    "start": 0,
    "perPage": 1,
    "count": 1
  },
  "results": [
    {
      "id": 1,
      "venueId": 1,
      "leadId": 2,
      "code": "HR5ZASGMQ1",
      "name": "Some Booking",
      "eventType": "Holiday",
      "companyId": 4,
      "company": {
        "id": 4,
        "businessName": "Some Business"
      },
      "contactId": 3,
      "contact": {
        "id": 3,
        "firstName": "Quamar",
        "lastName": "Boyer",
        "email": "example@domain.com",
        "phone": "+247-92-9848064"
      },
      "isConfidential": false,
      "currentStatus": 3,
      "totalAmount": 105,
      "totalTaxAmount": 5,
      "amountOutstanding": -425.3,
      "accountTimezone": null,
      "venueTimezone": "Australia/Brisbane",
      "createdDate": "2015-01-07 09:21:53 UTC",
      "modifiedDate": "2016-04-06 07:51:56 UTC",
      "bookingType": 1,
      "dateEventStart": "2015-06-01 00:00:00 UTC",
      "dateEventEnd": "2015-06-04 00:00:00 UTC",
      "convertedToTentative": "2016-02-23 00:00:00 UTC",
      "convertedToConfirmed": "2016-03-05 12:49:31 UTC",
      "convertedToCancelled": "2016-02-28 00:00:00 UTC",
      "isAccommIncluded": true,
      "dateAccomStart": "2015-06-01 00:00:00 UTC",
      "dateAccomEnd": "2015-06-27 00:00:00 UTC",
      "focRoomsDenominator": 5,
      "maxNumFocRoomsPerDay: 2,
      "hasPackages": true,
      "decisionDate": "",
      "canBeMoved": false,
      "bookedById": 123,
      "beoNumbers": ["11-1", "12-1", "13-2"],
      "isBeoFinalised": true,
      "beoFinalisedDate": "2015-02-09 03:37:39 UTC",
      "otaFolioRef": "ven1234",
      "accommCutOffDate": "2019-12-04 00:00:00 UTC",
      "accommCancellationDate": "2019-01-11 00:00:00 UTC",
      "accommChargingMethod": 2,
      "accommGuaranteeRequired": false,
      "accommExternalBlockId": "test 123",
    }
  ]
}
```
{% endtab %}
{% endtabs %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties. The per page value is required, for example {"perPage":10}

## Example Request

`Get a specific venue’s Booking List`

```javascript
{
  "perPage": 1
}
```

## currentStatus:

One of the following values:

* 1 = Prospective
* 2 = Tentative
* 3 = Confirmed
* 4 = Cancelled
* 5 = Ordering
* 8 = Not Accepted
* 9 = Prospective Hold

## Additional [Filter ](../../getting-started/interpreting-the-response/filtering.md)Properties

| Property           | Description             | Type                                                                     |
| ------------------ | ----------------------- | ------------------------------------------------------------------------ |
| modifiedDateBefore | Filter by Modified Date | [iVvy Timestamp Format](../../development-reference/timestamp-format.md) |
| modifiedDateAfter  | Filter by Modified Date | [iVvy Timestamp Format](../../development-reference/timestamp-format.md) |
