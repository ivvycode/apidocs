# Get Invoice

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="invoice?action=getInvoice" method="post" summary="Get Invoice" %}
{% swagger-description %}
Get details of an invoice
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The invoice identifier
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "id": 957114,
    "reference": "1007458",
    "title": "Deposit Invoice",
    "description": "Example Invoice Description",
    "currency": "AUD",
    "totalCost": 233.45,
    "totalTaxCost": 21.22,
    "amountPaid": 233.45,
    "toContactEmail": "example@ivvy.com",
    "toContactName": "Example Name",
    "currentStatus": 2,
    "createdDate": "2018-06-11 06:06:42 UTC",
    "issuedDate": "2018-06-11 06:06:42 UTC",
    "modifiedDate": "2018-06-11 06:06:43 UTC",
    "refType": 4,
    "refId": 92471,
    "taxRateUsed": null,
    "isTaxCharged": 1,
    "paymentDueDate": "2018-06-11 06:06:42 UTC",
    "eventId": null,
    "venueId": 1683,
    "toContactId": null,
    "payments": [
        {
            "id": 63791,
            "paymentId": 0,
            "receiptNum": 729424,
            "amountPaid": 233.45,
            "feeAmount": 3.45,
            "feePercentage": 1.5,
            "notes": "",
            "chequeNumber": null,
            "paymentMethod": 1,
            "customPaymentMethodId": null,
            "paidDate": "2018-06-11 06:06:42 UTC",
            "cardType": 3,
        }
    ],
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
    "toAddress": {
        "line1": 1,
        "line2": "",
        "line3": "",
        "line4": "",
        "city": "asdf",
        "stateCode": "QLD",
        "stateName": null,
        "countryCode": "AU",
        "countryName": null,
        "postalCode": 2222
    },
    "venueExTaxes": [
        {
            "taxId": 6064,
            "amount": 15,
            "taxRateId": 0,
            "taxRateAmount": 15,
            "taxRateAmountType": 2,
            "costcenterId": 4
        },
        {
            "taxId": 6221,
            "amount": 5,
            "taxRateId": 0,
            "taxRateAmount": 5,
            "taxRateAmountType": 2,
            "costcenterId": 4
        }
    ],
    "items": [
        {
            "description": "Deposit payment for Christmas Party",
            "quantity": 1,
            "unitCost": 230,
            "totalCost": 230,
            "totalTaxCost": 20.91,
            "amountPaid": 230,
            "refType": 500,
            "refId": 50,
            "ref2Id": 500,
            "costCenters": [
                {
                    "costcenterId": 1,
                    "totalCost": 100,
                    "totalTaxCost": 10
                },
                {
                    "costcenterId": 2,
                    "totalCost": 100,
                    "totalTaxCost": 10
                },
                {
                    "costcenterId": 3,
                    "totalCost": 30,
                    "totalTaxCost": 0.91
                },
            ]
        },
        {
            "description": "1.5% iVvy Marketplace transaction fee included in AU$233.45 payment made Jun 11, 2018",
            "quantity": 1,
            "unitCost": 3.45,
            "totalCost": 3.45,
            "totalTaxCost": 0.31,
            "amountPaid": 3.45,
            "refType": 103,
            "costCenters": [
                {
                    "costcenterId": 1,
                    "totalCost": 1.50,
                    "totalTaxCost": 0.15
                },
                {
                    "costcenterId": 2,
                    "totalCost": 1.50,
                    "totalTaxCost": 0.15
                },
                {
                    "costcenterId": 3,
                    "totalCost": 0.45,
                    "totalTaxCost": 0.01
                },
            ],
            "taxes": [
                {
                    "taxId": 1,
                    "amount": 427.3789,
                    "taxRateId": 0,
                    "taxRateAmount": 10,
                    "taxRateAmountType": 1,
                    "costcenterId": 1
                },
                {
                    "taxId": 5455,
                    "amount": 1.4514,
                    "taxRateId": 2,
                    "taxRateAmount": 10,
                    "taxRateAmountType": 1,
                    "costcenterId": 2
                },
                {
                    "taxId": 5485,
                    "amount": 104.0434,
                    "taxRateId": 0,
                    "taxRateAmount": 10,
                    "taxRateAmountType": 1,
                    "costcenterId": 3
                }
            ]
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get a specific invoice`

```javascript
{
  "id":15
}
```

## Returns

A collection object with the following properties in the results

| Property       | Description                                                                                                                                           |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| id             | The unique invoice identifier                                                                                                                         |
| reference      | The unique reference number of the invoice                                                                                                            |
| title          | The title of the invoice                                                                                                                              |
| description    | The description of the invoice                                                                                                                        |
| currency       | The currency of the invoice                                                                                                                           |
| totalCost      | The total of the invoice                                                                                                                              |
| totalTaxCost   | The tax of the invoice                                                                                                                                |
| amountPaid     | The amount paid against the invoice                                                                                                                   |
| toContactEmail | The contact email of the invoice                                                                                                                      |
| toContactName  | The contact name of the invoice                                                                                                                       |
| contact        | The contact details of the invoice                                                                                                                    |
| company        | The company details of the invoice                                                                                                                    |
| currentStatus  | The status of the invoice                                                                                                                             |
| createdDate    | The created date of the invoice                                                                                                                       |
| modifiedDate   | The modified date of the invoice                                                                                                                      |
| refType        | The reference type of the invoice                                                                                                                     |
| refId          | The reference Id of the invoice                                                                                                                       |
| taxRateUsed    | The tax rate percent applied to invoice                                                                                                               |
| isTaxCharged   | Whether tax charged on the invoice                                                                                                                    |
| paymentDueDate | Payment due date of the invoice                                                                                                                       |
| eventId        | Event Identifier to which the invoice belongs                                                                                                         |
| venueId        | Venue Identifier to which the invoice belongs                                                                                                         |
| toContactId    | Contact Id against which invoice is created                                                                                                           |
| toAddress      | The “to” Address of the invoice                                                                                                                       |
| bookingCode    | The unique reference code of the booking if refType is 4 (Venue Booking)                                                                              |
| bookingId      | The unique identifier of the booking if refType is 4 (Venue Booking)                                                                                  |
| items          | List of invoice items Item Details                                                                                                                    |
| payments       | List of payments of the invoice Payment Details                                                                                                       |
| refunds        | List of refunds of the invoice [Refund Details](get-invoice.md#refund-details)                                                                        |
| venueExTaxes   | List of [taxes](get-invoice.md#item-taxes-details) which are not included in item's total. These taxes are included in the total cost of the invoice. |

## Current status

| # | Description       |
| - | ----------------- |
| 0 | Not Paid          |
| 1 | Un-confirmed Paid |
| 2 | Paid              |
| 3 | Written Off       |
| 4 | Cancelled         |
| 5 | Refunded          |

## Reference type

| # | Description        |
| - | ------------------ |
| 0 | Custom             |
| 1 | Event Registration |
| 2 | Membership Sign Up |
| 3 | Membership Renewal |
| 4 | Venue Booking      |

## Refund Details

| Property       | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| id             | The unique identifier of the invoice refund                  |
| invoiceId      | The identifier of the invoice related to this invoice refund |
| refundId       | The identifier of the refund                                 |
| refundDate     | The refund timestamp of the refund                           |
| amountRefunded | The refund amount                                            |
| notes          | The refund notes                                             |
| refundMethodId | The refund method(if any selected)                           |
| createdDate    | The created date of the refund                               |
| modifiedDate   | The modified date of the refund                              |

## Address Details

| Property    | Description                                      |
| ----------- | ------------------------------------------------ |
| line1       | Line 1 of the address (part of the "street")     |
| line2       | Line 2 of the address (part of the "street")     |
| line3       | Line 3 of the address (part of the "street")     |
| line4       | Line 4 of the address (part of the "street")     |
| city        | The city name of the address                     |
| stateCode   | The state code of the address (e.g. QLD)         |
| stateName   | The state name of the address (e.g. Queensland)  |
| countryCode | The country code of the address (e.g. AU)        |
| countryName | The country name of the address (e.g. Australia) |
| postalCode  | The postal code of the address                   |

## Item Details

| Property     | Description                                                                                                                                                                                |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id           | The identifier of the item                                                                                                                                                                 |
| description  | The description of the item                                                                                                                                                                |
| quantity     | Quantity of the item                                                                                                                                                                       |
| unitCost     | The unit cost of the item                                                                                                                                                                  |
| totalCost    | The total cost of the item                                                                                                                                                                 |
| totalTaxCost | The tax of the item                                                                                                                                                                        |
| amountPaid   | The amount paid of the item'                                                                                                                                                               |
| refType      | The reference type of the item                                                                                                                                                             |
| refId        | The reference type of the item                                                                                                                                                             |
| ref2Id       | The reference type of the item                                                                                                                                                             |
| costCenters  | The total cost and total tax cost by cost center                                                                                                                                           |
| taxes        | The taxes applied to the item. Some information in the tax item might be empty if information is not available. ie. for old invoices. See Item Taxes Details for the data in each tax item |

## Item Taxes Details

| Property          | Description                                                                                                          |
| ----------------- | -------------------------------------------------------------------------------------------------------------------- |
| taxId             | The identifier of the tax                                                                                            |
| amount            | The amount of tax                                                                                                    |
| taxRateId         | The identifier of the rate that overrided the default tax rate. Zero (0) when the default tax rate is not overridden |
| taxRateAmount     | The rate at which the tax was calculated                                                                             |
| taxRateAmountType | The tax rate amount type: 1 = A percentage, 2 = An amount                                                            |
| costcenterId      | The identifier of the cost center to which the tax applies                                                           |

## Item Ref Type

Used to categorise the line based on the type of item sold. Note: This isn't linked to cost centres as a package can be a single line on an invoice, but revenue can be allocated to multiple cost centres.

| RefType | Description                                                     |
| ------- | --------------------------------------------------------------- |
| 0       | Unknown                                                         |
| 100     | Fee ( \[102] => Card Fee, \[103] => Payment Fee)                |
| 500     | Deposit                                                         |
| 501     | Package (refId = Venue Package id, ref2Id = Booking Package Id) |
| 502     | Invoice                                                         |
| 503     | Payment                                                         |
| 505     | Session                                                         |
| 506     | Menu Package                                                    |
| 507     | Beverage Package                                                |
| 508     | Resource                                                        |
| 509     | Product                                                         |
| 510     | Accommodation                                                   |
| 511     | Additional Line                                                 |

## Payment Details

| Property              | Description                                                                           |
| --------------------- | ------------------------------------------------------------------------------------- |
| id                    | The unique identifier of the payment                                                  |
| paymentId             | The identifier of the credit card payment transaction (if payment was by credit card) |
| receiptNum            | The receipt number of the payment                                                     |
| amountPaid            | The amount paid of the payment                                                        |
| notes                 | The notes of the payment                                                              |
| chequeNumber          | The chequeNumber of the payment                                                       |
| paymentMethod         | The payment method of the payment                                                     |
| customPaymentMethodId | The id of the custom payment method of the payment                                    |
| paidDate              | The paid timestamp of the payment                                                     |
| feePercentage         | The percentage fee included in amountPaid                                             |
| feeAmount             | The fee amount included in amountPaid                                                 |
| cardType              | The type of card used for a credit card payment                                       |

`Note about fee: If the payment is applied to multiple invoices, the fee amount is applied to the first invoice only.`

## Throws

| Code                 | Description            |
| -------------------- | ---------------------- |
| Specific Code: 24137 | Unable to find invoice |

The invoice identifier must be provided as part of this call to fetch the specific invoice. E.g. {"id":1} can be used to fetch the details of an invoice with the identifier of 1.
