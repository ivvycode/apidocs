# Get Invoice List

## Description

Get list of invoices.

## Api Url

`[PlatformAddress]/api/1.0/invoice?action=getInvoiceList`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| perPage | The number of invoices to get in a single api call | Required | integer |
| start | The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\) | Required | integer |

## Additional [Filter ](../interpreting-the-response/filtering.md)Properties

| Property | Description | Type |
| --- | --- | --- |
| fromModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| toModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| venueId | Filter invoices that belong to a specific Venue | integer |
| refType | Filter by a specific reference type. The[ reference type](get-invoice-list.md#reference-type) of the invoice | integer |

## Reference type

| \# | Description |
| --- | --- |
| 0 | Custom |
| 1 | Event Registration |
| 2 | Membership Sign Up |
| 3 | Membership Renewal |
| 4 | Venue Booking |

## Returns

A collection object with the following properties in the results

| Property | Description |
| --- | --- |
| id | The unique invoice identifier |
| reference | The unique reference number of the invoice |
| title | The title of the invoice |
| description | The description of the invoice |
| currency | The currency of the invoice |
| totalCost | The total of the invoice |
| totalTaxCost | The tax of the invoice |
| amountPaid | The amount paid against the invoice |
| toContactEmail | The contact email of the invoice |
| toContactName | The contact name of the invoice |
| currentStatus | [The status of the invoice](get-invoice-list.md#current-status) |
| createdDate | The created date of the invoice |
| modifiedDate | The modified date of the invoice |
| refType | The reference type of the invoice |
| refId | The reference Id of the invoice |
| taxRateUsed | The tax rate percent applied to invoice |
| isTaxCharged | Whether tax charged on the invoice |
| paymentDueDate | Payment due date of the invoice |
| eventId | Event Identifier to which invoice is belongs to |
| venueId | Venue Identifier to which invoice is belongs to |
| toContactId | Contact Id against which invoice is created |
| toAddress | [The “to” Address of the invoice](get-invoice-list.md#address-details) |
| bookingCode | The unique reference code of the booking if refType is 4 \(Venue Booking\) |

## Current status

| \# | Description |
| --- | --- |
| 0 | Not Paid |
| 1 | Un-confirmed Paid |
| 2 | Paid |
| 3 | Written Off |
| 4 | Cancelled |
| 5 | Refunded |

## Address Details

| Property | Description |
| --- | --- |
| line1 | Line 1 of the address \(part of the "street"\) |
| line2 | Line 2 of the address \(part of the "street"\) |
| line3 | Line 3 of the address \(part of the "street"\) |
| line4 | Line 4 of the address \(part of the "street"\) |
| city | The city name of the address |
| stateCode | The state code of the address \(e.g. QLD\) |
| stateName | The state name of the address \(e.g. Queensland\) |
| countryCode | The country code of the address \(e.g. AU\) |
| countryName | The country name of the address \(e.g. Australia\) |
| postalCode | The postal code of the address |

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

## Example Response

```javascript
{
  "meta": {
    "totalResults": 29016,
    "start": 0,
    "perPage": 2,
    "count": 2
  },
  "results": [
    {
      "id": 15,
      "reference": 100000157,
      "title": "test",
      "description": null,
      "currency": "AUD",
      "totalCost": 150,
      "totalTaxCost": 13.636363636364,
      "amountPaid": 150,
      "toContactEmail": "wd42nc6d@h2k5lftg.com",
      "toContactName": "wd42nc6d h2k5lftg",
      "currentStatus": 2,
      "createdDate": "2010-06-07 12:21:40 UTC",
      "modifiedDate": "2015-07-18 01:32:39 UTC",
      "refType": 1,
      "refId": 107,
      "taxRateUsed": 10,
      "isTaxCharged": 1,
      "paymentDueDate": "",
      "eventId": 56,
      "venueId": null,
      "toContactId": 25148,
      "toAddress": {
        "line1": "66949VGT",
        "line2": "9J08OO8E",
        "line3": "3JVPX2E",
        "line4": "8G6MLU9M",
        "city": "2G6NP196",
        "stateCode": "QLD",
        "stateName": null,
        "countryCode": "AU",
        "countryName": null,
        "postalCode": "5SA19NAQ"
      },
      "bookingCode": null
    },
    {
      "id": 64,
      "reference": 100000645,
      "title": null,
      "description": null,
      "currency": "AUD",
      "totalCost": 200,
      "totalTaxCost": 18.181818181818,
      "amountPaid": 200,
      "toContactEmail": "wd42nc6d@h2k5lftg.com",
      "toContactName": "wd42nc6d h2k5lftg",
      "currentStatus": 2,
      "createdDate": "2010-06-27 22:56:23 UTC",
      "modifiedDate": "2015-05-19 02:15:04 UTC",
      "refType": 1,
      "refId": 168,
      "taxRateUsed": 10,
      "isTaxCharged": 1,
      "paymentDueDate": "",
      "eventId": 59,
      "venueId": null,
      "toContactId": 25148,
      "toAddress": {
        "line1": "1NVLK5BI",
        "line2": "A07E92TC",
        "line3": "33JKPTGA",
        "line4": "BNF1DO08",
        "city": "546O5YBN",
        "stateCode": "QLD",
        "stateName": null,
        "countryCode": "AU",
        "countryName": null,
        "postalCode": "S90I9GG"
      },
      "bookingCode": null
    }
  ]
}
```

