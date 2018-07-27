# Add Refund To Booking

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addRefundToBooking" path="" %}
{% api-method-summary %}
Add Refund to Booking
{% endapi-method-summary %}

{% api-method-description %}
Add a refund to a booking using this api. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking belongs
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=true %}
The unique id of the booking to which the refund will be added
{% endapi-method-parameter %}

{% api-method-parameter name="refund" type="object" required=false %}
The payment details to add to the booking
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "Success": true,
  "refundDetails": [
    {
      "invoiceId": 1736,
      "refundId": 180
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

All invoices of the booking will be checked for the refunded amount and if the amount is refundable then only the refund amount will be added to invoice.

## Example Request

`Add refund to booking`

```javascript
{
  "venueId": 2,
  "bookingId": 2,
  "refund": {
    "refundDate": "2015-01-22 00:00:00 UTC",
    "amount": 100,
    "notes": "Note for refund"
  }
}
```

## Payment Details

| Property | Description | Required |
| --- | --- | --- |
| refundDate | The date & time of the refund | timestamp in UTC |
| amount | The refund amount | number |
| notes | Additional notes about the refund | string |

## Returns

| Property | Description |
| --- | --- |
| success | Whether or not the refund was added to the booking |
| refundDetails | A collection of invoiceId and refundId values |

## Refund Details

| Property | Description |
| --- | --- |
| invoiceId | The unique id of the invoice |
| refundId | The id of the invoice refund |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24149 | The refund details are invalid |
| Specific Code: 24145 | The booking does not have an amount that can be refunded |
| Specific Code: 24146 | Cannot refund more than the total amount payable on a booking |
| Specific Code: 24147 | The refund amount must be greater than zero |
| Specific Code: 24148 | The full refund amount could not be applied to the booking |

