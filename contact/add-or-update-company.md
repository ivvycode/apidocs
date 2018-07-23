# Add or Update Company

### Description

Add or update company detail.

### API URL

`[PlatformAddress]/api/1.0/contact?action=addOrUpdateCompany`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The company’s identifier. \(Leave empty to add the company to the system.\) | Required | integer |
| externalId | Optionally a unique identifier of the company that is managed by an external application |  |  |
| businessName | The company's business name | Mandatory if adding a new company |  |
| tradingName | The company's trading name |  |  |
| businessNumber | The company's registration number |  |  |
| phone | The company's phone number |  |  |
| fax | The company's fax number |  |  |
| website | The company's website |  |  |
| email | The company's email address |  |  |
| address | The company’s address. This is an an object with the [keys](add-or-update-company.md#keys) |  |  |

### Keys

| keys |
| --- |
| line1 |
| line2 |
| line3 |
| line4 |
| city |
| stateCode \(e.g: QLD\) |
| countryCode \(e.g: AU\) |
| postalCode |

### Returns

| Property | Description |
| --- | --- |
| success | If the company was successfully added or updated |
| id | The unique identifier for the company |
| message | Message of the failure \(if success was false\) |

This call takes values for a company, and either

1. Updates the values for that company \(after you have provided an id in the parameters\), or
2. Adds the company to the system \(if the id parameter is missing\)

The result of this call will contain the status of the result \(either true or false\) and the company identifier of the updated or newly created company.

The properties of the company currently supported are:

* businessName
* externalId
* tradingName
* businessNumber
* phone
* fax
* website
* email
* address
  * This is an object

### `Adding a company`

### Example Request

```javascript
{
  "businessName": "New Company",
  "tradingName": "ABC",
  "email": "company@test.com",
  "address": {
    "line1": "address line 1",
    "line2": "address line 2",
    "stateCode": "QLD",
    "postalCode": "4227",
    "countryCode": "AU"
  }
}
```

### Example Response

```javascript
{
  "success": true,
  "id": 1618
}
```

### `Updating a company`

### Example Request

```javascript
{
  "id": 1618,
  "businessName": "Updated Company name",
  "address": {
    "line1": "address line 11",
    "line2": "address line 22",
    "stateCode": "QLD",
    "postalCode": "4227",
    "countryCode": "AU"
  }
}
```

### Example Response

```javascript
{
  "id": 1618
}
```

