# Get Company

### Description

Get company detail.

### API URL

`[PlatformAddress]/api/1.0/contact?action=getCompany`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The company’s identifier | Required | integer |

### Returns

| Property | Description |
| --- | --- |
| id | The unique identifier for the company |
| externalId | Optionally a unique identifier of the company that is managed by an external application |
| businessName | The company's business name |
| tradingName | The company's trading name |
| businessNumber | The company's registration number |
| phone | The company's phone number |
| fax | The company's fax number |
| website | The company's website |
| email | The company's email address |
| address | The company’s address. This is an an object with the [keys](get-company.md#keys) |
| modifiedDate | The modified date of the company |

### Keys

| **keys** |
| --- |
| line1 |
| line2 |
| line3 |
| line4 |
| city |
| stateCode \(e.g: QLD\) |
| countryCode \(e.g: AU\) |
| postalCode |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24153 | Unable to find company |

The company identifier must be provided to fetch a specific company from the system.

### Example Request

`Get a specific company`

```javascript
{ 
  "id":6
}
```

### Example Response

```javascript
{
  "id": "25146",
  "businessName": "Test",
  "tradingName": "Test Trading",
  "businessNumber": "1234586",
  "email": "company@test.com",
  "phone": "0455550000",
  "fax": "0455550125",
  "website": "www.test.com",
  "address": {
    "line1": "Street Number",
    "line2": "Street Name",
    "line3": "",
    "line4": "",
    "city": "Gold Coast",
    "stateCode": "QLD",
    "countryCode": "AU",
    "postalCode": "4227"
  }
}
```

