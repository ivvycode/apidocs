# Company Endpoint

This notification will be sent when a company has been modified or created. <ul><li>Company has been updated.</li><li>Company has been created.</li><li>Company has been deleted.</li></ul>

## Company has been created.

### Subject 

CompanyAdded

### Body

```json
{
    "data": {... JSON Response from getCompany API }
}
```

## Company has been updated.

### Subject: 

CompanyUpdated

### Body

```json
{
    "data": {... JSON Response from getCompany API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Company has been deleted.

### Subject

CompanyDeleted

### Body

```json
{
    "companyId": 123
}
```



