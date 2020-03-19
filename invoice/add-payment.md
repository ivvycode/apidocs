# Add Payment

{% api-method method="post" host="\[PlatformAddress\]/api/1.0" path="/invoice?action=AddPayment" %}
{% api-method-summary %}
Add Payment
{% endapi-method-summary %}

{% api-method-description %}
Add a payment against a specific invoice within iVvy.   
  
Payments will only be accepted if that amount is outstanding on the invoice. Over pays will not be accepted.  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="invoiceId" type="integer" required=true %}
The unique id of the invoice to which the payment is applied
{% endapi-method-parameter %}

{% api-method-parameter name="paidDate" type="string" required=true %}
The date & time of the payment \(datetime\)
{% endapi-method-parameter %}

{% api-method-parameter name="amountPaid" type="number" required=true %}
The payment amount
{% endapi-method-parameter %}

{% api-method-parameter name="paymentMethod" type="integer" required=true %}
The payment method
{% endapi-method-parameter %}

{% api-method-parameter name="customPaymentMethodId" type="integer" required=false %}
The id of custom payment method
The paymentMethod should be "Unknown" when the customPaymentMethodId is used.
{% endapi-method-parameter %}

{% api-method-parameter name="receiptNum" type="string" required=true %}
A receipt number
{% endapi-method-parameter %}

{% api-method-parameter name="reconciledDate" type="string" required=false %}
The date & time the payment was reconciled
{% endapi-method-parameter %}

{% api-method-parameter name="cardType" type="string" required=true %}
The credit card type  
Required if paymentMethod = credit card
{% endapi-method-parameter %}

{% api-method-parameter name="feePercentage" type="number" required=false %}
The credit card fee percentage. The fee amount must be included in amountPaid
{% endapi-method-parameter %}

{% api-method-parameter name="feeExcludedTaxIds" type="array" required=false %}
An array of tax ids which will be excluded from the payment.
{% endapi-method-parameter %}

{% api-method-parameter name="chequeNumber" type="string" required=true %}
The cheque number   
Required if paymentMethod = "cheque"  
{% endapi-method-parameter %}

{% api-method-parameter name="chequeDrawerName" type="string" required=false %}
The cheque drawer number   
If paymentMethod = “cheque”
{% endapi-method-parameter %}

{% api-method-parameter name="chequeBankBranch" type="string" required=false %}
The cheque bank branch   
If paymentMethod = “cheque”
{% endapi-method-parameter %}

{% api-method-parameter name="eftTransferDate" type="string" required=false %}
The payment transfer date \(datetime\)  
If paymentMethod = “direct deposit”
{% endapi-method-parameter %}

{% api-method-parameter name="eftPaymentReference" type="string" required=false %}
The payment reference   
If paymentMethod = “direct deposit”
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "Success": true,
  "Id": 5452
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

```text
Example: Add Payment to an invoice
```

```text
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

0 = Unknown  
1 = Credit Card  
2 = BPay  
3 = Direct Deposit  
4 = PayPal  
5 = Cheque  
6 = Cash  
8 = Accounts Receivable  
9 = EFTPOS  
10 = WriteOff  
11 = Point of Sale  
12 = Wire Transfer

## cardType

0 = Unknown  
1 = Visa  
2 = Master Card  
3 = Amex  
4 = Diners

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the payment was added to the invoice |
| id | The unique identifier of the payment |

## Throws

| Code | Description |
| :--- | :--- |
| 24235 | The request is empty |
| 24236 | Invalid payment method |
| 24237 | Cannot use "gateway" or "paymentId" to make the invoice payment |
| 24238 | Unable to find invoice |
| 24239 | The payment details are invalid |
| 24240 | An unknown error has occurred |

