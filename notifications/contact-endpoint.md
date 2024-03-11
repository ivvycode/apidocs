# Contact Endpoint

This notification will be sent when a contact has been modified or created.

Here are the `Body` of the example notification messages after parse.

## Contact has been created.
```json
{
    "data": {... JSON Response from getContact API }
}
```

## Contact has been updated.
```json
{
    "data": {... JSON Response from getContact API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Contact has been deleted.

```json
{
    "contactId": 123
}
```


