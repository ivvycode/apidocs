# Add or Update Lead Channel

{% swagger baseUrl="[PlatformAddress]/api/1.0/crm?action=addOrUpdateLeadChannel" method="post" summary="Add or Update Lead Channel" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the lead channel (Leave empty if adding a new lead channel)
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name of the crm lead channel (Required when the ID parameter is missing)
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

### Add Lead Channel

```javascript
{
  "name": "Referal Channel",
}
```

### Update Lead Channel

```javascript
{
  "id": 755,
  "name": "Another name"
}
```

## Returns

| Property | Description                               |
| -------- | ----------------------------------------- |
| success  | Whether or not the lead channel was added |
| id       | The unique id of the lead channel         |

## Throws

| Code                 | Description                          |
| -------------------- | ------------------------------------ |
| Specific Code: 24376 | The crm lead channel does not exist  |
| Specific Code: 24377 | The crm lead channel is not editable |
| Specific Code: 24378 | An error has occurred                |
| Specific Code: 24379 | The request contains invalid data    |
| Specific Code: 24380 | The request contains invalid data    |

This call takes values for a lead channel, and either

1. Updates the values for that lead channel (after you have provided an id in the parameters), or
2.  Adds the lead channel to the system (if the id parameter is missing) 1. The result of this call will contain the status of the result (either

    true or false) and the lead channel identifier of the updated or newly

    created lead channel.
