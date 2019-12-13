# Add or Update Cost Center

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/account?action=addOrUpdateCostCenter" path="" %}
{% api-method-summary %}
Add or Update Cost Center
{% endapi-method-summary %}

{% api-method-description %}
Add or update cost center details to the account.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The unique identifier of the cost centre  
\(Leave empty to add the cost centre to the account\)
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
The name of the cost centre
{% endapi-method-parameter %}

{% api-method-parameter name="code" type="string" required=true %}
The code of the cost centre
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
The complete description of the coast centre
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "Success": true,
  "Id": 5452
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

| Property | Description |
| :--- | :--- |
| success | Whether or not the cost center was added to the account |
| id | The unique identifier of the cost center |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24150 | Account does not exist |
| Specific Code: 24150 | The cost centers details are invalid |

