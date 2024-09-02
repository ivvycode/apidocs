# Add or Update Cost Center

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="account?action=addOrUpdateCostCenter" method="post" summary="Add or Update Cost Center" %}
{% swagger-description %}
Add or update cost center details to the account.
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique identifier of the cost center

\


(Leave empty to add the cost center to the account)
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name of the cost center. Required when adding a new cost center.
{% endswagger-parameter %}

{% swagger-parameter name="code" type="string" in="path" %}
The code of the cost center. Required when adding a new cost center.
{% endswagger-parameter %}

{% swagger-parameter name="description" type="string" in="path" %}
The complete description of the cost center
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "Success": true,
  "Id": 5452
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Example: Add a cost center to an account`

```javascript
{
  "name": "test cost center",
  "code": "AB12",
  "description": "The complete description of the cost center"
}
```

## Returns

| Property | Description                                             |
| -------- | ------------------------------------------------------- |
| success  | Whether or not the cost center was added to the account |
| id       | The unique identifier of the cost center                |

## Throws

| Code                 | Description                          |
| -------------------- | ------------------------------------ |
| Specific Code: 24150 | Account does not exist               |
| Specific Code: 24150 | The cost centers details are invalid |
