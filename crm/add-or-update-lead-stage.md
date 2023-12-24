# Add or Update Lead Stage

{% swagger baseUrl="[PlatformAddress]/api/1.0/crm?action=addOrUpdateLeadStage" method="post" summary="Add or Update Lead Stage" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the lead stage (Leave empty if adding a new lead stage)
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name of the crm lead stage (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="colour" type="string" in="path" %}
The colour for the stage will help to identify and group leads/opportunities
{% endswagger-parameter %}

{% swagger-parameter name="applyTo" type="strings" in="path" %}
Whether lead stage applies to lead or opportunity (Required when the ID parameter is missing)
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

## applyTo

Equal to one of the following values

* 1 = Opportunity
* 2 = Lead

## Example Request

### Add Lead Stage

```javascript
{
  "name": "Referal Lead",
  "applyTo": 1,
}
```

### Update Lead Stage

```javascript
{
  "id": 755,
  "colour": "#7ee546"
}
```

## Returns

| Property | Description                             |
| -------- | --------------------------------------- |
| success  | Whether or not the lead stage was added |
| id       | The unique id of the lead stage         |

## Throws

| Code                 | Description                        |
| -------------------- | ---------------------------------- |
| Specific Code: 24320 | The crm lead stage does not exist  |
| Specific Code: 24321 | The crm lead stage is not editable |
| Specific Code: 24322 | An error has occurred              |
| Specific Code: 24323 | The request contains invalid data  |
| Specific Code: 24324 | The request contains invalid data  |

This call takes values for a lead stage, and either

1. Updates the values for that lead stage (after you have provided an id in the parameters), or
2.  Adds the lead stage to the system (if the id parameter is missing) 1. The result of this call will contain the status of the result (either

    true or false) and the lead stage identifier of the updated or newly

    created lead stage.
