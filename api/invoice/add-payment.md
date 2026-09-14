# Add Payment

## Add Payment

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/invoice?action=addPayment`

Add a payment against a specific invoice within iVvy.Payments will only be accepted if that amount is outstanding on the invoice. Over pays will not be accepted.

#### Request Body

| Name                  | Type    | Description                                                                                   |
| --------------------- | ------- | --------------------------------------------------------------------------------------------- |
| invoiceId             | integer | The unique id of the invoice to which the payment is applied                                  |
| paidDate              | string  | The date & time of the payment (datetime)                                                     |
| amountPaid            | number  | The payment amount                                                                            |
| paymentMethod         | integer | The payment method                                                                            |
| customPaymentMethodId | integer | The custom payment method id Required if paymentMethod = custom                               |
| receiptNum            | string  | A receipt number                                                                              |
| reconciledDate        | string  | The date & time the payment was reconciled                                                    |
| cardType              | string  | <p>The credit card type</p><p>\</p><p>Required if paymentMethod = credit card</p>             |
| feePercentage         | number  | The credit card fee percentage.                                                               |
| feeAmount             | number  | The credit card fee amount flat. If this is passed, feePercentage will be ignored.            |
| feeExcludedTaxIds     | array   | An array of tax ids which will be excluded from the payment.                                  |
| chequeNumber          | string  | <p>The cheque number</p><p>\</p><p>Required if paymentMethod = "cheque"</p>                   |
| chequeDrawerName      | string  | <p>The cheque drawer number</p><p>\</p><p>If paymentMethod = “cheque”</p>                     |
| chequeBankBranch      | string  | <p>The cheque bank branch</p><p>\</p><p>If paymentMethod = “cheque”</p>                       |
| eftTransferDate       | string  | <p>The payment transfer date (datetime)</p><p>\</p><p>If paymentMethod = “direct deposit”</p> |
| eftPaymentReference   | string  | <p>The payment reference</p><p>\</p><p>If paymentMethod = “direct deposit”</p>                |

{% tabs %}
{% tab title="200 " %}
```javascript
{
  "Success": true,
  "Id": 5452
}
```
{% endtab %}
{% endtabs %}

## Example Request

```
Example: Add Payment to an invoice
```

```
{
  "invoiceId": "156",
  "paidDate": "2018-07-24 00:00:00",
  "amountPaid": 10,
  "paymentMethod": 8,
  "receiptNum": "123",
  "feePercentage": 10
}
```

## paymentMethod

0 = Unknown\
1 = Credit Card\
2 = BPay\
3 = Direct Deposit\
4 = PayPal\
5 = Cheque\
6 = Cash\
8 = Accounts Receivable\
9 = EFTPOS\
10 = WriteOff\
11 = Point of Sale\
12 = Wire Transfer\
13 = Custom

## cardType

0 = Unknown\
1 = Visa\
2 = Master Card\
3 = Amex\
4 = Diners

## Returns

| Property | Description                                         |
| -------- | --------------------------------------------------- |
| success  | Whether or not the payment was added to the invoice |
| id       | The unique identifier of the payment                |

## Throws

| Code  | Description                                                     |
| ----- | --------------------------------------------------------------- |
| 24235 | The request is empty                                            |
| 24236 | Invalid payment method                                          |
| 24237 | Cannot use "gateway" or "paymentId" to make the invoice payment |
| 24238 | Unable to find invoice                                          |
| 24239 | The payment details are invalid                                 |
| 24240 | An unknown error has occurred                                   |
