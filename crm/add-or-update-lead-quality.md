# Add or Update Lead Quality

{% swagger baseUrl="[PlatformAddress]/api/1.0/crm?action=addOrUpdateLeadQuality" method="post" summary="Add or Update Lead Quality" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the lead quality (Leave empty if adding a new lead quality)
{% endswagger-parameter %}

{% swagger-parameter name="label" type="string" in="path" %}
The label of the crm lead quality (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="showOnDash" type="boolean" in="path" %}
Whether or not to include leads/opportunities assigned this quality on the venue reporting dashboard
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

### Add Lead Quality

```javascript
{
  "label": "A Grade",
  "showOnDash": false,
}
```

### Update Lead Quality

```javascript
{
  "id": 755,
  "label": "Updated Quality"
}
```

## Returns

| Property | Description                               |
| -------- | ----------------------------------------- |
| success  | Whether or not the lead quality was added |
| id       | The unique id of the lead quality         |

## Throws

| Code                 | Description                         |
| -------------------- | ----------------------------------- |
| Specific Code: 24304 | The crm lead quality does not exist |
| Specific Code: 24305 | An error has occurred               |
| Specific Code: 24306 | The request contains invalid data   |
| Specific Code: 24307 | The request contains invalid data   |

This call takes values for a lead quality, and either

1. Updates the values for that lead quality (after you have provided an id in the parameters), or
2.  Adds the lead quality to the system (if the id parameter is missing) 1. The result of this call will contain the status of the result (either

    true or false) and the lead quality identifier of the updated or newly

    created lead quality.
