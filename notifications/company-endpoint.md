# Company Endpoint

This notification will be sent when a company has been modified or created.

Here are the `Body` of the example notification messages after parse.

## Company has been created.
```json
{
    "data": {... JSON Response from getCompany API }
}
```
Subject: **CompanyAdded**


## Company has been updated.
```json
{
    "data": {... JSON Response from getCompany API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **CompanyUpdated**

## Company has been deleted.

```json
{
    "companyId": 123
}
```
Subject: **CompanyDeleted**


