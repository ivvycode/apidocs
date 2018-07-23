# Get Cost Center List

### Description

Fetches the list of cost centers in the account. No request params required.

### Api Url

`[PlatformAddress]/api/1.0/account?action=getCostCenterList`

### Returns

| Property | Description |
| --- | --- |
| id | The unique identifier of the cost center |
| name | The name of the cost center |
| code | The code of the cost center |
| description | The complete description of the cost center |
| defaultType | Set if one of the default cost centers |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24150 | Account does not exist |

### Example Response

`Example: get cost center list of the account`

```javascript
{
  "meta": {
    "totalResults": 2,
    "start": 0,
    "perPage": 2,
    "count": 2
  },
  "results": [
    {
      "id": 5451,
      "name": "test cost center",
      "code": 2,
      "description": null,
      "defaultType": null
    },
    {
      "id": 5452,
      "name": "test cost center",
      "code": "AB12",
      "description": null,
      "defaultType": null
    }
  ]
}
```

