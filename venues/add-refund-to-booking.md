# Add Refund To Booking

### Description

We can add a refund to a booking using this API. The venueId, Booking Id and refund details are required. All invoice of the booking will be check for the refunded amount and if the amount is refundable then only the refund amount will be added to invoice.

### API URL

`[PlatformAddress]/api/1.0/venue?action=addRefundToBooking`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| venueId | The unique id of the venue to which the booking belongs | Required | integer |
| bookingId | The unique id of the booking to which the refund will be added | Required | integer |
| refund | [The payment details to add to the booking](add-refund-to-booking.md#payment-details) |  |  |

### Payment Details

| Property | Description | Required |
| --- | --- | --- |
| refundDate | The date & time of the refund | timestamp in UTC |
| amount | The refund amount | number |
| notes | Additional notes about the refund | string |

### Returns

| Property | Description |
| --- | --- |
| success | Whether or not the refund was added to the booking |
| refundDetails | A collection of invoiceId and refundId values |

### Refund Details

| Property | Description |
| --- | --- |
| invoiceId | The unique id of the invoice |
| refundId | The id of the invoice refund |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24149 | The refund details are invalid |
| Specific Code: 24145 | The booking does not have an amount that can be refunded |
| Specific Code: 24146 | Cannot refund more than the total amount payable on a booking |
| Specific Code: 24147 | The refund amount must be greater than zero |
| Specific Code: 24148 | The full refund amount could not be applied to the booking |

### Example Request

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

### Example Response

```javascript
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

