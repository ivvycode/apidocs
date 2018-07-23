# Add Payment To Booking

### Description

We can add the payment details of a booking using this API. The venueId, Booking Id and payment details are required. This will also create a payment and booking invoice.

### API URL

`[PlatformAddress]/api/1.0/venue?action=addPaymentToBooking`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| venueId | The unique id of the venue to which the booking belongs | Required | integer |
| bookingId | The unique id of the booking to which the payment will be added | Required | integer |
| payment | The payment details to add to the booking |  |  |

### Payment Details

| Property | Description | Type |
| --- | --- | --- | --- |
| paidDate | The date & time of the payment | Timestamp in UTC |
| amountPaid | The payment amount | number |
| paymentMethod | [The payment method](add-payment-to-booking.md#payment-methods) |  |
| receiptNum | A receipt number of the payment transaction | string |
| notes | Additional notes about the payment | string |

### Payment methods

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

### Returns

| Property | Description |
| --- | --- |
| success | Whether or not the payment was added to the booking |
| invoiceId | The unique id of the invoice to which the payment was added |
| paymentId | The unique identifier of the payment made |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24136 | The payment details are invalid |

### Example Request

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

### Example Response

```javascript
{
  "Success": true,
  "invoiceId": 1736,
  "paymentId": 758
}
```

