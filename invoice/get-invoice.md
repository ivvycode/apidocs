# Get Invoice

## Description

Get invoice details.

## Api Url

`[PlatformAddress]/api/1.0/invoice?action=getInvoice`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The invoice identifier | Required | integer |

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
| currentStatus | The status of the invoice |
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
| toAddress | The “to” Address of the invoice |
| bookingCode | The unique reference code of the booking if refType is 4 \(Venue Booking\) |
| items | List of invoice items Item Details |
| payments | List of payments of the invoice Payment Details |

## Current status

| \# | Description |
| --- | --- |
| 0 | Not Paid |
| 1 | Un-confirmed Paid |
| 2 | Paid |
| 3 | Written Off |
| 4 | Cancelled |
| 5 | Refunded |

## Reference type

| \# | Description |
| --- | --- |
| 0 | Custom |
| 1 | Event Registration |
| 2 | Membership Sign Up |
| 3 | Membership Renewal |
| 4 | Venue Booking |

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

## Item Details

| Property | Description |
| --- | --- |
| description | The description of the item |
| quantity | Quantity of the item |
| unitCost | The unit cost of the item |
| totalCost | The total cost of the item |
| totalTaxCost | The tax of the item |
| amountPaid | The amount paid of the item' |
| refType | The reference type of the item |

## Payment Details

| Property | Description |
| --- | --- |
| paymentId | The identifier of the payment |
| receiptNum | The receipt number of the payment |
| amountPaid | The amount paid of the payment |
| notes | The notes of the payment |
| chequeNumber | The chequeNumber of the payment |
| paymentMethod | The payment method of the payment |
| paidDate | The paid timestamp of the payment |
| feePercentage | The percentage fee included in amountPaid |
| feeAmount | The fee amount included in amountPaid |

`Note about fee: If the payment is applied to multiple invoices, the fee amount is applied to the first invoice only.`

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24137 | Unable to find invoice |

The invoice identifier must be provided as part of this call to fetch the specific invoice. E.g. {"id":1} can be used to fetch the details of an invoice with the identifier of 1.

## Example Request

`Get a specific invoice`

```javascript
{ 
  "id":15
}
```

## Example Response

```javascript
{
  "id": 15,
  "reference": 100000157,
  "title": "test",
  "description": null,
  "currency": "AUD",
  "totalCost": 150,
  "totalTaxCost": 13.64,
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
  "items": [
    {
      "description": "Registration 107 of event National Technology Conference",
      "quantity": 1,
      "unitCost": 150,
      "totalCost": 150,
      "totalTaxCost": 13.64,
      "amountPaid": 150,
      "refType": 0
    }
  ],
  "payments": [
    {
      "paymentId": null,
      "receiptNum": "6WCQRIXZ",
      "amountPaid": 150,
      "feeAmount": 0,
      "feePercentage": 0,
      "notes": "8TPCEN81",
      "chequeNumber": null,
      "paymentMethod": 6,
      "paidDate": "2011-07-04 23:00:00 UTC"
    }
  ]
}
```

