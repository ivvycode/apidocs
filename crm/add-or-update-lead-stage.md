# Add or Update Lead Stage

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=addOrUpdateLeadStage" path="" %}
{% api-method-summary %}
Add or Update Lead Stage
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the lead stage
\(Leave empty if adding a new lead stage\)
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
The name of the crm lead stage
\(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="colour" type="string" required=false %}
The colour for the stage will help to identify and group leads/opportunities
{% endapi-method-parameter %}

{% api-method-parameter name="applyTo" type="strings" required=false %}
Whether lead stage [applies to](add-or-update-lead-stage.md#applies-to) lead or opportunity
\(Required when the ID parameter is missing\)
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "success": true,
  "id": 755
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Applies To

| 1 | Opportunity |
| 2 | Lead |

## Example Request

### Add Lead Stage

```javascript
{
  "name": "Referal Lead",
  "appliesTo": 1,
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

| Property | Description |
| :--- | :--- |
| success | Whether or not the lead stage was added |
| id | The unique id of the lead stage |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24320 | The crm lead stage does not exist |
| Specific Code: 24321 | The crm lead stage is not editable |
| Specific Code: 24322 | An error has occurred |
| Specific Code: 24323 | The request contains invalid data |
| Specific Code: 24324 | The request contains invalid data |

This call takes values for a lead stage, and either

1. Updates the values for that lead stage \(after  you have provided an id in the parameters\), or
2. Adds the lead stage to the system \(if the id parameter is missing\) 1. The result of this call will contain the status of the result \(either

   true or false\) and the lead stage identifier of the updated or newly

   created lead stage.

