# Invoice Endpoint

This notification will occur when a modification to an invoice occurs. This includes when payments are applied against an invoice. <ul><li>Invoice is created</li><li>Invoice is updated</li><li>Payment is applied to invoice</li></ul>

## Invoice is created.

### Subject
InvoiceAdded

### Body

```json
{
    "data": {... JSON Response from getInvoice API }
}
```

## Invoice is updated.

### Subject
InvoiceUpdated

### Body

```json
{
    "data": {... JSON Response from getInvoice API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Payment is applied to invoice

### Subject
InvoiceUpdated

### Body

```json
{
    "data": {... JSON Response from getInvoice API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```