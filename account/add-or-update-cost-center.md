# Add or Update Cost Center

### Description

Add or update cost center details to the account. The cost center name and code are required.

### Api Url

`[PlatformAddress]/api/1.0/account?action=addOrUpdateCostCenter`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The unique identifier of the cost center \(Leave empty to add the cost center to the account.\) | Required | number |
| name | The name of the cost center | Required | string |
| code | The code of the cost center | Required | string |
| description | The complete description of the cost center |  | string |

### Returns

| Property | Description |
| --- | --- |
| success | Whether or not the cost center was added to the account |
| id | The unique identifier of the cost center |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24150 | Account does not exist |
| Specific Code: 24150 | The cost centers details are invalid |

### Example Request

`Example: Add a cost center to an account`

```javascript
{
  "name": "test cost center",
  "code": "AB12",
  "description": "The complete description of the cost center"
}
```

### Example Response

```javascript
{
  "Success": true,
  "Id": 5452
}
```

