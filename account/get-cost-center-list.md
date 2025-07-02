# Get Cost Center List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="account?action=getCostCenterList" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
Fetches the list of cost centers in the account. No request params required.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Returns

| Property | Description |
| :--- | :--- |
| id | The unique identifier of the cost center |
| name | The name of the cost center |
| code | The code of the cost center |
| description | The complete description of the cost center |
| defaultType | Set if one of the default cost centers. See [Default Type](get-cost-center-list.md#default-type)  |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24150 | Account does not exist |


## Default Type

| Type  | Description       |
| ----- | ------------------|
| 1     | Other             |
| 2     | Food              |
| 3     | Beverage          |
| 4     | Audio Visual      |
| 5     | Room Hire         |
| 6     | Accommodation     |
| 7     | Service Fees      |