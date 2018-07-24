# Add or Update Contact

### Description

Add or update contact details.

### API URL

`[PlatformAddress]/api/1.0/contact?action=addOrUpdateContact`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The contact’s identifier. \(Leave empty to add the contact to the system.\) |  | integer |
| firstName | The contact’s first name | Required \(when the id parameter is missing\) | string |
| lastName | The contact’s last name | Required \(when the id parameter is missing\) | string |
| email | The contact’s email address | Must be a valid email. | string |
| phone | The contact’s phone number | Must be a valid phone number. | string |
| groups | The array of subscription groups to set for the contact | Note : this list will override any groups currently set for the contact | string |
| customFields | The array of custom fields to set on the contact | Each field will be validated depending on the type of field that is being set. |  |
| companies | The array of companies to set the contact. | Each values will be validated depending on the type of field as well as it will verify that the given company is exist or not. |  |

### Returns

| Property | Description |
| --- | --- |
| success | If the contact was successfully added or updated |
| id | The unique identifier for the contact |
| message | Message of the failure \(if success was false\) |

This call takes values for a contact, and either

1. Updates the values for that contact \(after you have provided an id in the parameters\), or
2. Adds the contact to the system \(if the id parameter is missing\)

The result of this call will contain the status of the result \(either true or false\) and the contact identifier of the updated or newly created contact.

The properties of the contact currently supported are:

* firstName
* lastName
* email
* phone
* groups
  * This is an array of group objects with the ‘groupId’ key.
* customFields
  * This is an array of custom field objects with ‘fieldId’ and ‘value’ keys
* Companies
  * This is an array of companies Ids

### `Adding a contact`

### Example Request

```javascript
{
  "id": 33884,
  "firstName": "Bobby",
  "groups": [
    {
      "groupId": 10
    }
  ],
  "customFields": [
    {
      "fieldId": 33443,
      "value": "No"
    }
  ],
  "companies": [
    4,
    5
  ]
}
```

### Example Response

```javascript
{
  "id":33884
}
```

### `Updating a contact`

### Example Request

`Note : the groups will be set to only group 10, destroying the existing value`

```javascript
{
  "id":33884,
  "firstName":"Bobby",
  "groups":[{"groupId":10}],
  "customFields":[{"fieldId":33443,"value":"No"}],
  "companies":[4,5]
}
```

### Example Response

```javascript
{
   "id":33884
}
```

