# Add or Update Lead Source

{% swagger baseUrl="[PlatformAddress]/api/1.0/crm?action=addOrUpdateLeadSource" method="post" summary="Add or Update Lead Source" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the lead source (Leave empty if adding a new lead source)
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name of the crm lead source (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="cost" type="string" in="path" %}
The cost for usage of the crm lead source
{% endswagger-parameter %}

{% swagger-parameter name="colour" type="string" in="path" %}
The colour for the source will help to identify and group leads/opportunities
{% endswagger-parameter %}

{% swagger-parameter name="isReferral" type="strings" in="path" %}
Whether or not this source is referral
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

### Add Lead Source

```javascript
{
  "name": "Referal Source",
  "isReferral": true,
}
```

### Update Lead Source

```javascript
{
  "id": 755,
  "description": "#Description of source"
}
```

## Returns

| Property | Description                              |
| -------- | ---------------------------------------- |
| success  | Whether or not the lead source was added |
| id       | The unique id of the lead source         |

## Throws

| Code                 | Description                         |
| -------------------- | ----------------------------------- |
| Specific Code: 24325 | The crm lead source does not exist  |
| Specific Code: 24326 | The crm lead source is not editable |
| Specific Code: 24327 | An error has occurred               |
| Specific Code: 24328 | The request contains invalid data   |
| Specific Code: 24329 | The request contains invalid data   |

This call takes values for a lead source, and either

1. Updates the values for that lead source (after you have provided an id in the parameters), or
2.  Adds the lead source to the system (if the id parameter is missing) 1. The result of this call will contain the status of the result (either

    true or false) and the lead source identifier of the updated or newly

    created lead source.
