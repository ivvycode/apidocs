# Get Credit Note List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="invoice?action=getCreditNoteList" %}
{% api-method-summary %}
Get Invoice List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of Credit Notes
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="perPage" type="integer" required=true %}
The number of credit notes to get in a single api call
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
        "totalResults": 124,
        "start": 0,
        "perPage": 2,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "reference": "CN10000001",
            "title": "Event Testing: *Registration 7*",
            "notes": null,
            "currency": "AUD",
            "totalAmount": 500,
            "totalTaxAmount": 45.45,
            "amountAllocated": null,
            "amountRefunded": null,
            "createdDate": "2015-12-28 08:31:50 UTC",
            "modifiedDate": "2015-12-28 08:31:50 UTC",
            "refType": 1,
            "refId": 7,
            "eventId": 2,
            "venueId": null,
            "contactId": 153,
            "companyId": null,
            "invoiceId": null
        },
        {
            "id": 3,
            "reference": "CN10000003",
            "title": "*Deposit Invoice*",
            "notes": null,
            "currency": "AUD",
            "totalAmount": null,
            "totalTaxAmount": null,
            "amountAllocated": null,
            "amountRefunded": null,
            "createdDate": "2015-12-28 12:43:02 UTC",
            "modifiedDate": "2015-12-28 12:43:02 UTC",
            "refType": 4,
            "refId": 1437,
            "eventId": null,
            "venueId": null,
            "contactId": 0,
            "companyId": null,
            "invoiceId": null
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get credit note list`

```javascript
{
  "start":0,
  "perPage" 10,
  "filter": {
    "venueId" : 1
  }
}
```

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
| refType | The [reference type](get-credit-note-list.md#reference-type) of the credit note |
| refId | The reference Id of the credit note |
| eventId | Event Identifier to which the credit note belongs |
| venueId | Venue Identifier to which the credit note belongs |
| companyId | Company Identifier to which the credit note belongs |
| invoiceId | Invoice Identifier from which the credit note is created |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the credit notes the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

