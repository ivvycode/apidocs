# Invoice Endpoint

This notification will occur when a modification to an invoice occurs. This includes when payments are applied against an invoice. <ul><li>Invoice is created</li><li>Invoice is updated</li><li>Payment is applied to invoice</li></ul>

## Invoice is created.
```json
{
    "data": {... JSON Response from getInvoice API }
}
```
Subject: **InvoiceAdded**


## Invoice is updated.
```json
{
    "data": {... JSON Response from getInvoice API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **InvoiceUpdated**


## Payment is applied to invoice

```json
{
    "data": {... JSON Response from getInvoice API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **InvoiceUpdated**



