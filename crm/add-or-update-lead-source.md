# Add or Update Lead Source

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=addOrUpdateLeadSource" path="" %}
{% api-method-summary %}
Add or Update Lead Source
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the lead source \(Leave empty if adding a new lead source\)
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
The name of the crm lead source \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="cost" type="string" required=false %}
The cost for usage of the crm lead source
{% endapi-method-parameter %}

{% api-method-parameter name="colour" type="string" required=false %}
The colour for the source will help to identify and group leads/opportunities
{% endapi-method-parameter %}

{% api-method-parameter name="isReferral" type="strings" required=false %}
Whether or not this source is referral
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

| Property | Description |
| :--- | :--- |
| success | Whether or not the lead source was added |
| id | The unique id of the lead source |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24325 | The crm lead source does not exist |
| Specific Code: 24326 | The crm lead source is not editable |
| Specific Code: 24327 | An error has occurred |
| Specific Code: 24328 | The request contains invalid data |
| Specific Code: 24329 | The request contains invalid data |

This call takes values for a lead source, and either

1. Updates the values for that lead source \(after  you have provided an id in the parameters\), or
2. Adds the lead source to the system \(if the id parameter is missing\) 1. The result of this call will contain the status of the result \(either

   true or false\) and the lead source identifier of the updated or newly

   created lead source.

