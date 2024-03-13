# Contact Endpoint

This notification will be sent when a contact has been modified or created. <ul><li>Contact has been updated</li><li>Contact has been created</li><li>Contact has been deleted</li></ul>

## Contact has been created.

### Subject
ContactAdded

### Body

```json
{
    "data": {... JSON Response from getContact API }
}
```

## Contact has been updated.

### Subject
ContactUpdated

### Body

```json
{
    "data": {... JSON Response from getContact API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Contact has been deleted.

### Subject
ContactDeleted

### Body


```json
{
    "contactId": 123
}
```


