# Add or Update Cost Center

## Add or Update Cost Center

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/account?action=addOrUpdateCostCenter`

Add or update cost center details to the account.

#### Path Parameters

| Name        | Type    | Description                                                                                                       |
| ----------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| id          | integer | <p>The unique identifier of the cost center</p><p>\</p><p>(Leave empty to add the cost center to the account)</p> |
| name        | string  | The name of the cost center. Required when adding a new cost center.                                              |
| code        | string  | The code of the cost center. Required when adding a new cost center.                                              |
| description | string  | The complete description of the cost center                                                                       |

{% tabs %}
{% tab title="200 " %}
```
{
  "Success": true,
  "Id": 5452
}
```
{% endtab %}
{% endtabs %}

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
