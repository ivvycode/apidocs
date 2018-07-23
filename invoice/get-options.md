# Get Options

### Description

The invoice and item response contains a field called "refType". These are constants in the iVvy system to match the invoice or item to a specific entity. To find out a description of what these constants refer to, you can make a call to the api to get the complete list

### Api Url

`[PlatformAddress]/api/1.0/invoice?action=getOptions`

### Parameters

Parameters No parameters required.

### Returns

| Property | Description |
| --- | --- |
| invoiceRefTypes | The refType identifier and description of refTypes found in the invoice response. |
| invoiceLineRefTypes | The refType identifier and description of refTypes found in the items of the invoice response. |
| paymentMethods | The complete list of payment methods that might appear against a payment made on an invoice |

