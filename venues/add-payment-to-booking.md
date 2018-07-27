# Add Payment To Booking

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addPaymentToBooking" path="" %}
{% api-method-summary %}
Add Payment To Booking
{% endapi-method-summary %}

{% api-method-description %}
Add payment details to a booking. This will also generate an invoice that the payment is applied to. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking belongs
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=true %}
The unique id of the booking to which the payment will be added
{% endapi-method-parameter %}

{% api-method-parameter name="payment" type="object" required=false %}
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
  "invoiceId": 1736,
  "paymentId": 758
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Add payment to booking`

```javascript
{
  "venueId": 2,
  "bookingId": 2,
  "payment": {
    "paidDate": "2015-01-22 00:00:00",
    "amountPaid": 100,
    "paymentMethod": 6,
    "receiptNum": 12345,
    "notes": "Note for payment"
  }
}
```

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| venueId | The unique id of the venue to which the booking belongs | Required | integer |
| bookingId | The unique id of the booking to which the payment will be added | Required | integer |
| payment | The payment details to add to the booking |  |  |

## Payment Details

| Property | Description | Type |
| --- | --- | --- | --- |
| paidDate | The date & time of the payment | Timestamp in UTC |
| amountPaid | The payment amount | number |
| paymentMethod | [The payment method](add-payment-to-booking.md#payment-methods) |  |
| receiptNum | A receipt number of the payment transaction | string |
| notes | Additional notes about the payment | string |

## Payment methods

| \# | Description |
| --- | --- |
| 0 | Unknown |
| 1 | Credit Card |
| 2 | BPay |
| 3 | Direct Deposit |
| 4 | PayPal |
| 5 | Cheque |
| 6 | Cash |
| 7 | Custom Gateway |
| 8 | Accounts Receivable |
| 9 | EFTPOS |
| 10 | WriteOff |
| 11 | Point of Sale |
| 12 | Wire Transfer |

## Returns

| Property | Description |
| --- | --- |
| success | Whether or not the payment was added to the booking |
| invoiceId | The unique id of the invoice to which the payment was added |
| paymentId | The unique identifier of the payment made |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24136 | The payment details are invalid |

