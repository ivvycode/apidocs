# Add Payment

{% swagger baseUrl="[PlatformAddress]/api/1.0" path="/invoice?action=AddPayment" method="post" summary="Add Payment" %}
{% swagger-description %}
Add a payment against a specific invoice within iVvy.Payments will only be accepted if that amount is outstanding on the invoice. Over pays will not be accepted.
{% endswagger-description %}

{% swagger-parameter name="invoiceId" type="integer" in="body" %}
The unique id of the invoice to which the payment is applied
{% endswagger-parameter %}

{% swagger-parameter name="paidDate" type="string" in="body" %}
The date & time of the payment (datetime)
{% endswagger-parameter %}

{% swagger-parameter name="amountPaid" type="number" in="body" %}
The payment amount
{% endswagger-parameter %}

{% swagger-parameter name="paymentMethod" type="integer" in="body" %}
The payment method
{% endswagger-parameter %}

{% swagger-parameter name="customPaymentMethodId" type="integer" in="body" %}
The custom payment method id Required if paymentMethod = custom
{% endswagger-parameter %}

{% swagger-parameter name="receiptNum" type="string" in="body" %}
A receipt number
{% endswagger-parameter %}

{% swagger-parameter name="reconciledDate" type="string" in="body" %}
The date & time the payment was reconciled
{% endswagger-parameter %}

{% swagger-parameter name="cardType" type="string" in="body" %}
The credit card type

\


Required if paymentMethod = credit card
{% endswagger-parameter %}

{% swagger-parameter name="feePercentage" type="number" in="body" %}
The credit card fee percentage.
{% endswagger-parameter %}

{% swagger-parameter name="feeAmount" type="number" in="body" %}
The credit card fee amount flat. If this is passed, feePercentage will be ignored.
{% endswagger-parameter %}

{% swagger-parameter name="feeExcludedTaxIds" type="array" in="body" %}
An array of tax ids which will be excluded from the payment.
{% endswagger-parameter %}

{% swagger-parameter name="chequeNumber" type="string" in="body" %}
The cheque number

\


Required if paymentMethod = "cheque"
{% endswagger-parameter %}

{% swagger-parameter name="chequeDrawerName" type="string" in="body" %}
The cheque drawer number

\


If paymentMethod = “cheque”
{% endswagger-parameter %}

{% swagger-parameter name="chequeBankBranch" type="string" in="body" %}
The cheque bank branch

\


If paymentMethod = “cheque”
{% endswagger-parameter %}

{% swagger-parameter name="eftTransferDate" type="string" in="body" %}
The payment transfer date (datetime)

\


If paymentMethod = “direct deposit”
{% endswagger-parameter %}

{% swagger-parameter name="eftPaymentReference" type="string" in="body" %}
The payment reference

\


If paymentMethod = “direct deposit”
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "Success": true,
  "Id": 5452
}
```
{% endswagger-response %}
{% endswagger %}

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
