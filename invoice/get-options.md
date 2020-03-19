# Get Options

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/invoice?action=getOptions" path="" %}
{% api-method-summary %}
Get Options
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

No Parameters Required

The invoice and item response contains a field called "refType". These are constants in the iVvy system to match the invoice or item to a specific entity. To find out a description of what these constants refer to, you can make a call to the api to get the complete list

## Returns

| Property | Description |
| :--- | :--- |
| invoiceRefTypes | The refType identifier and description of refTypes found in the invoice response. |
| invoiceLineRefTypes | The refType identifier and description of refTypes found in the items of the invoice response. |
| paymentMethods | The complete list of standard payment methods that might appear against a payment made on an invoice |
| customPaymentMethods | The complete list of custom payment methods that might appear against a payment made on an invoice |

