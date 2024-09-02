# Add Payment To Booking

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=addPaymentToBooking" method="post" summary="Add Payment To Booking" %}
{% swagger-description %}
Add a payment to a booking. This will also generate an invoice to apply the payment to.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the booking belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="path" %}
The unique id of the booking to which the payment will be added
{% endswagger-parameter %}

{% swagger-parameter name="payment" type="object" in="path" %}
The payment details to add to the booking
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "Success": true,
  "invoiceId": 1736,
  "paymentId": 758
}
```
{% endswagger-response %}
{% endswagger %}

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

## Payment Details

| Property      | Description                                                     | Type             |
| ------------- | --------------------------------------------------------------- | ---------------- |
| paidDate      | The date & time of the payment                                  | Timestamp in UTC |
| amountPaid    | The payment amount                                              | number           |
| paymentMethod | [The payment method](add-payment-to-booking.md#payment-methods) |                  |
| receiptNum    | A receipt number of the payment transaction                     | string           |
| notes         | Additional notes about the payment                              | string           |

## Payment methods

| #  | Description         |
| -- | ------------------- |
| 0  | Unknown             |
| 1  | Credit Card         |
| 2  | BPay                |
| 3  | Direct Deposit      |
| 4  | PayPal              |
| 5  | Cheque              |
| 6  | Cash                |
| 7  | Custom Gateway      |
| 8  | Accounts Receivable |
| 9  | EFTPOS              |
| 10 | WriteOff            |
| 11 | Point of Sale       |
| 12 | Wire Transfer       |

## Returns

| Property  | Description                                                 |
| --------- | ----------------------------------------------------------- |
| success   | Whether or not the payment was added to the booking         |
| invoiceId | The unique id of the invoice to which the payment was added |
| paymentId | The unique identifier of the payment made                   |

## Throws

| Code                 | Description                     |
| -------------------- | ------------------------------- |
| Specific Code: 24136 | The payment details are invalid |
