# Get Invoice List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/invoice?action=getInvoiceList" path="" %}
{% api-method-summary %}
Get Invoice List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of invoices
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="perPage" type="integer" required=true %}
The number of invoices to get in a single api call
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=true %}
The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\)
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
        "totalResults": 2,
        "start": 0,
        "perPage": 2,
        "count": 2
    },
    "results": [
        {
            "id": 409615,
            "reference": 1007127,
            "title": "Tax Invoice",
            "description": "Final Invoice",
            "currency": "AUD",
            "totalCost": 40,
            "totalTaxCost": 18.19,
            "amountPaid": 0,
            "toContactEmail": "17ZDUR@B4H6N9.com",
            "toContactName": "iVvy",
            "currentStatus": 4,
            "createdDate": "2014-01-13 06:07:44 UTC",
            "issuedDate": "2014-01-13 06:07:44 UTC",
            "modifiedDate": "2014-01-13 06:09:25 UTC",
            "refType": 4,
            "refId": 3707,
            "taxRateUsed": 10,
            "isTaxCharged": 1,
            "paymentDueDate": "2014-01-13 06:07:44 UTC",
            "eventId": null,
            "venueId": 1459,
            "toContactId": null,
            "payments": null,
            "toAddress": {
                "line1": "BUC2MRQY",
                "line2": "6P0L654O",
                "line3": "C46O8GXU",
                "line4": "27YU00V8",
                "city": "NRII7OB",
                "stateCode": "QLD",
                "stateName": null,
                "countryCode": "AU",
                "countryName": null,
                "postalCode": "90UX5DUX"
            },
            "bookingCode": "WLBTCHTT39",
            "contact": {
                "id": 580,
                "firstName": "First",
                "lastName": "last",
                "email": "filrst.last@email.com",
                "phone": 614535435
            },
            "company": {
                "id": 214,
                "businessName": "Company BusinessName",
                "businessNumber": "BUS123",
                "phone": null,
                "email": company@owner.com
            },
        },
        {
            "id": 409619,
            "reference": 1007128,
            "title": "Deposit Invoice",
            "description": "Deposit Invoice",
            "currency": "AUD",
            "totalCost": 200,
            "totalTaxCost": 18.18,
            "amountPaid": 200,
            "toContactEmail": "2CBCVL@BEW6CI.com",
            "toContactName": "iVvy",
            "currentStatus": 2,
            "createdDate": "2014-01-13 06:09:31 UTC",
            "issuedDate": "2014-01-13 06:09:31 UTC",
            "modifiedDate": "2018-09-20 03:51:44 UTC",
            "refType": 4,
            "refId": 3707,
            "taxRateUsed": 10,
            "isTaxCharged": 1,
            "paymentDueDate": "2014-01-09 00:00:00 UTC",
            "eventId": null,
            "venueId": 1459,
            "toContactId": null,
            "payments": null,
            "toAddress": {
                "line1": "ARZGCTX1",
                "line2": "IN49FIT",
                "line3": "AGDMN9TH",
                "line4": "BAXME6O1",
                "city": "62HFZEQG",
                "stateCode": "QLD",
                "stateName": null,
                "countryCode": "AU",
                "countryName": null,
                "postalCode": "8NSP0QE0"
            },
            "bookingCode": "WLBTCHTT39",
            "contact": {
                "id": 580,
                "firstName": "First",
                "lastName": "last",
                "email": "filrst.last@email.com",
                "phone": 614535435
            },
            "company": null,
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Additional [Filter ](../getting-started/interpreting-the-response/filtering.md)Properties

| Property | Description | Type |
| :--- | :--- | :--- |
| fromModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| includePaymentDetails | Filter by Payment Details | boolean |
| toModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| venueId | Filter invoices that belong to a specific Venue | integer |
| refType | Filter by a specific reference type. The[ reference type](get-invoice-list.md#reference-type) of the invoice | integer |

## Reference type

| \# | Description |
| :--- | :--- |
| 0 | Custom |
| 1 | Event Registration |
| 2 | Membership Sign Up |
| 3 | Membership Renewal |
| 4 | Venue Booking |

## Returns

A collection object with the following properties in the results

| Property | Description |
| :--- | :--- |
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
| contact | The contact details of the invoice |
| company | The company details of the invoice |
| currentStatus | [The status of the invoice](get-invoice-list.md#current-status) |
| createdDate | The created date of the invoice |
| modifiedDate | The modified date of the invoice |
| refType | The reference type of the invoice |
| refId | The reference Id of the invoice |
| taxRateUsed | The tax rate percent applied to invoice |
| isTaxCharged | Whether tax charged on the invoice |
| paymentDueDate | Payment due date of the invoice |
| eventId | Event Identifier to which the invoice belongs |
| venueId | Venue Identifier to which the invoice belongs |
| toContactId | Contact Id against which invoice is created |
| toAddress | [The “to” Address of the invoice](get-invoice-list.md#address-details) |
| bookingCode | The unique reference code of the booking if refType is 4 \(Venue Booking\) |
| bookingId | The unique identifier of the booking if refType is 4 \(Venue Booking\) |
| payments | List of payments of the invoice Payment Details |

## Current status

| \# | Description |
| :--- | :--- |
| 0 | Not Paid |
| 1 | Un-confirmed Paid |
| 2 | Paid |
| 3 | Written Off |
| 4 | Cancelled |
| 5 | Refunded |

## Address Details

| Property | Description |
| :--- | :--- |
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

## Payment Details

| Property | Description |
| :--- | :--- |
| id | The unique identifier of the payment |
| paymentId | The identifier of the credit card payment transaction \(if payment was by credit card\) |
| receiptNum | The receipt number of the payment |
| amountPaid | The amount paid of the payment |
| notes | The notes of the payment |
| chequeNumber | The chequeNumber of the payment |
| paymentMethod | The payment method of the payment |
| paidDate | The paid timestamp of the payment |
| feePercentage | The percentage fee included in amountPaid |
| feeAmount | The fee amount included in amountPaid |
| invoiceId | The unique invoice identifier |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the invoices the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

