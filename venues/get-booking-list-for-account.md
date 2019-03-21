# Get Booking List For Account

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getBookingListForAccount" path="" %}
{% api-method-summary %}
Get Booking List for Account
{% endapi-method-summary %}

{% api-method-description %}
A collection of bookings for the account that the user has access \(as opposed to bookings for a single venue in an account for get Bookings List\)
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="perPage" type="integer" required=true %}
The number of bookings to get in a single call
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
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
      "dateEventStart": "2015-06-01 00:00:00 UTC",
      "dateEventEnd": "2015-06-04 00:00:00 UTC",
      "isAccommIncluded": true,
      "dateAccomStart": "2015-06-01 00:00:00 UTC",
      "dateAccomEnd": "2015-06-27 00:00:00 UTC",
      "focRoomsDenominator": 5,
      "maxNumFocRoomsPerDay: 2,
      "hasPackages": true,
      "decisionDate": "",
      "canBeMoved": false,
      "bookedById": 123,
      "isBeoFinalised": true,
      "beoFinalisedDate": "2015-02-09 03:37:39 UTC"
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties. The per page value is required, for example {"perPage":10}

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

## Additional [Filter ](../getting-started/interpreting-the-response/filtering.md)Properties

| Property | Description | Type |
| :--- | :--- | :--- |
| modifiedDateBefore | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| modifiedDateAfter | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |

