# Get Credit Note

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="invoice?action=getCreditNote" %}
{% api-method-summary %}
Get Credit Note
{% endapi-method-summary %}

{% api-method-description %}
Get details of a credit note
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The credit note identifier
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "id": 716,
    "reference": "CN10000129",
    "title": "Test Credit Note",
    "notes": "",
    "currency": "AUD",
    "totalAmount": 1118.4,
    "totalTaxAmount": 100,
    "amountAllocated": 1118.4,
    "amountRefunded": null,
    "createdDate": "2021-02-16 05:10:55 UTC",
    "modifiedDate": "2021-02-16 05:15:42 UTC",
    "refType": 4,
    "refId": 27398,
    "eventId": null,
    "venueId": 1,
    "contactId": null,
    "companyId": 854,
    "address": {
        "line1": "2/1 New Castle Stree",
        "line2": "",
        "line3": "",
        "line4": "",
        "city": "Burleigh Heads",
        "stateCode": "QLD",
        "countryCode": "AU",
        "postalCode": 4220
    },
    "taxes": [
        {
            "taxId": 5455,
            "amount": 100,
            "costcenterId": 0,
            "taxRateId": 0,
            "taxRateAmount": 0,
            "taxRateAmountType": 0
        }
    ],
    "items": [
        {
            "id": 551,
            "description": "Accommodation: Room \"Room 4\" arrive 02/01/2021 depart 03/01/2021",
            "quantity": 1,
            "unitCost": 1000,
            "totalCost": 1000,
            "totalTaxCost": 90.91,
            "amountPaid": null,
            "refType": 510,
            "costCenters": [
                {
                    "costcenterId": 6,
                    "totalCost": 1000,
                    "totalTaxCost": 90.909
                }
            ],
            "taxes": [
                {
                    "taxId": 5455,
                    "amount": 90.909,
                    "taxRateId": 0,
                    "taxRateAmount": 0,
                    "taxRateAmountType": 0,
                    "costcenterId": 0
                }
            ]
        },
        {
            "id": 552,
            "description": "Service Fee: Accomm SF (10%) on Room \"Room 4\"",
            "quantity": 1,
            "unitCost": 100,
            "totalCost": 100,
            "totalTaxCost": 9.09,
            "amountPaid": null,
            "refType": 513,
            "costCenters": [
                {
                    "costcenterId": 6,
                    "totalCost": 100.000091,
                    "totalTaxCost": 9.091
                }
            ],
            "taxes": [
                {
                    "taxId": 5455,
                    "amount": 9.091,
                    "taxRateId": 0,
                    "taxRateAmount": 0,
                    "taxRateAmountType": 0,
                    "costcenterId": 0
                }
            ]
        },
        {
            "id": 553,
            "description": "Balance Adjustment",
            "quantity": 1,
            "unitCost": 18.4,
            "totalCost": 18.4,
            "totalTaxCost": 0,
            "amountPaid": null,
            "refType": 504,
            "costCenters": [
                {
                    "costcenterId": 16105,
                    "totalCost": 500,
                    "totalTaxCost": 45.455
                }
            ],
            "taxes": []
        }
    ],
    "allocations": [
        {
            "invoiceId": 4842,
            "creditDate": "2021-02-16 05:16:17",
            "amountAllocated": 1000.0,
            "notes": null
        }
    ],
    "refunds": [
        {
            "refundId": 195,
            "refundDate": "2021-02-18 00:05:15",
            "amountRefunded": 118.4,
            "notes": "Jus refunded."
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get a specific credit note`

```javascript
{
  "id" : 716
}
```

## Returns

A collection object with the following properties in the results

| Property | Description |
| :--- | :--- |
| id | The unique credit note identifier |
| reference | The unique reference number of the credit note |
| title | The title of the credit note |
| notes | The description of the credit note |
| currency | The currency of the credit note |
| totalAmount | The total of the credit note |
| totalTaxAmount | The tax of the credit note |
| amountAllocated | Sum of the allocated amounts to invoices from the credit note |
| amountRefunded | Sum of the refunded amounts from the credit note |
| createdDate | The created date of the credit note |
| modifiedDate | The modified date of the credit note |
| refType | The [reference type](get-credit-note.md#reference-type) of the credit note |
| refId | The reference Id of the credit note |
| eventId | Event Identifier to which the credit note belongs |
| venueId | Venue Identifier to which the credit note belongs |
| companyId | Company Identifier to which the credit note belongs |
| invoiceId | Invoice Identifier from which the credit note is created |
| address | The "to" address of the credit note. See [Address Details](get-credit-note.md#address-details) |
| taxes | List of individual taxes with their amount of the credit note. See [Tax Details](get-credit-note.md#tax-details) |
| items | List of items the credit note items. See [Item Details](get-credit-note.md#item-details) |
| allocations | List of credit note allocations. See [Allocation Details](get-credit-note.md#allocation-details) |
| refunds | List of credit note refunds. See [Refund Details](get-credit-note.md#refund-details) |

## Reference type

| \# | Description |
| :--- | :--- |
| 0 | Custom |
| 1 | Event Registration |
| 2 | Membership Sign Up |
| 3 | Membership Renewal |
| 4 | Venue Booking |

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

## Item Details

| Property | Description |
| :--- | :--- |
| id | The identifier of the item |
| description | The description of the item |
| quantity | Quantity of the item |
| unitCost | The unit cost of the item |
| totalCost | The total cost of the item |
| totalTaxCost | The tax of the item |
| amountPaid | The amount paid of the item' |
| refType | The [reference type](get-credit-note.md#item-ref-type) of the item |
| costCenters | The total cost and total tax cost by cost center |
| taxes | The taxes applied to the item. Some information in the tax item might be empty if information is not available. ie. for old credit notes. See [Tax Details](get-credit-note.md#tax-details) for the data in each tax item |

## Tax Details

| Property | Description |
| :--- | :--- |
| taxId | The identifier of the tax |
| amount | The amount of tax |
| taxRateId | The identifier of the rate that overrided the default tax rate. Zero \(0\) when the default tax rate is not overridden |
| taxRateAmount | The rate at which the tax was calculated |
| taxRateAmountType | The tax rate amount type: 1 = A percentage, 2 = An amount |
| costcenterId | The identifier of the cost center to which the tax applies |

## Item Ref Type

Used to categorise the line based on the type of item sold. Note: This isn't linked to cost centres as a package can be a single line on an invoice, but revenue can be allocated to multiple cost centres.

| RefType | Description |
| :--- | :--- |
| 0 | Unknown |
| 100 | Fee \( \[102\] =&gt; Card Fee, \[103\] =&gt; Payment Fee\) |
| 500 | Deposit |
| 501 | Package |
| 502 | Invoice |
| 503 | Payment |
| 505 | Session |
| 506 | Menu Package |
| 507 | Beverage Package |
| 508 | Resource |
| 509 | Product |
| 510 | Accommodation |
| 511 | Additional Line |
| 512 | Invoice Payment Fee |
| 513 | Service Fee |

## Allocation Details

| Property | Description |
| :--- | :--- |
| invoiceId | The invoice identifier to which the amount allocated |
| creditDate | The date when the amount was allocated |
| amountAllocated | The allocated amount |
| notes | The notes of the allocation |

## Refund Details

| Property | Description |
| :--- | :--- |
| refundId | The refund identifier |
| refundDate | The date when the amount was refunded |
| amountRefunded | The refunded amount |
| notes | The notes of the refund |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24406 | The credit note does not exist |

The credit note identifier must be provided as part of this call to fetch the specific credit note. E.g. {"id":1} can be used to fetch the details of an credit note with the identifier of 1.

