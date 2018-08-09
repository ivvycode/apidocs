# Add Payment

{% api-method method="post" host="\[PlatformAddress\]/api/1.0" path="/invoice?action=AddPayment" %}
{% api-method-summary %}
Add Payment
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
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
 The payment method \( “accounts receivable”, “bpay”, “cash”, “cheque”, “credit card”, “direct deposit”, “eftpos”, “paypal”, “point of sale”, “wire transfer”, “unknown”\)
{% endapi-method-parameter %}

{% api-method-parameter name="receiptNum" type="string" required=true %}
 A receipt number
{% endapi-method-parameter %}

{% api-method-parameter name="reconciledDate" type="string" required=false %}
 The date & time the payment was reconciled
{% endapi-method-parameter %}

{% api-method-parameter name="cardType" type="string" required=false %}
 The credit card type \(“unknown”, “visa”, “master”, “amex”, “diners”\)
{% endapi-method-parameter %}

{% api-method-parameter name="feePercentage" type="string" required=false %}
 The credit card fee percentage. The fee amount must be included in amountPaid
{% endapi-method-parameter %}

{% api-method-parameter name="chequeNumber" type="string" required=true %}
The cheque number
{% endapi-method-parameter %}

{% api-method-parameter name="chequeDrawerName" type="string" required=false %}
 The cheque drawer number \(\(If paymentMethod = “cheque”\)\)
{% endapi-method-parameter %}

{% api-method-parameter name="chequeBankBranch" type="string" required=false %}
 The cheque bank branch \(If paymentMethod = “cheque”**\)**
{% endapi-method-parameter %}

{% api-method-parameter name="eftTransferDate" type="string" required=false %}
The payment transfer date \(datetime\) paymentMethod = “direct deposit”
{% endapi-method-parameter %}

{% api-method-parameter name="eftPaymentReference" type="string" required=false %}
The payment reference paymentMethod = “direct deposit”  
Pa{
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
| 24240 | Other error |
| 24241 | An unknown error has occurred |