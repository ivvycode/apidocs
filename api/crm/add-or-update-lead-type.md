# Add or Update Lead Type

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="crm?action=addOrUpdateLeadType" method="post" summary="Add or Update Lead Type" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the lead type (Leave empty if adding a new lead type)
{% endswagger-parameter %}

{% swagger-parameter name="type" type="string" in="path" %}
The name of the crm lead type (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true,
  "id": 755
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

### Add Lead Type

```javascript
{
  "type": "Referal Type",
}
```

### Update Lead Type

```javascript
{
  "id": 755,
  "type": "Another name"
}
```

## Returns

| Property | Description                            |
| -------- | -------------------------------------- |
| success  | Whether or not the lead type was added |
| id       | The unique id of the lead type         |

## Throws

| Code                 | Description                       |
| -------------------- | --------------------------------- |
| Specific Code: 24381 | The crm lead type does not exist  |
| Specific Code: 24382 | An error has occurred             |
| Specific Code: 24383 | The request contains invalid data |
| Specific Code: 24384 | The request contains invalid data |

This call takes values for a lead type, and either

1. Updates the values for that lead type (after you have provided an id in the parameters), or
2.  Adds the lead type to the system (if the id parameter is missing) 1. The result of this call will contain the status of the result (either

    true or false) and the lead type identifier of the updated or newly

    created lead type.
