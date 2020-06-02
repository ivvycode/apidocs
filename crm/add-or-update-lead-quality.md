# Add or Update Lead Quality

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=addOrUpdateLeadQuality" path="" %}
{% api-method-summary %}
Add or Update Lead Quality
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the lead quality
\(Leave empty if adding a new lead quality\)
{% endapi-method-parameter %}

{% api-method-parameter name="label" type="string" required=false %}
The label of the crm lead quality
\(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="showOnDash" type="boolean" required=false %}
Whether or not to include leads/opportunities assigned this quality on the venue reporting dashboard
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

| Property | Description |
| :--- | :--- |
| success | Whether or not the lead quality was added |
| id | The unique id of the lead quality |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24304 | The crm lead quality does not exist |
| Specific Code: 24305 | An error has occurred |
| Specific Code: 24306 | The request contains invalid data |
| Specific Code: 24307 | The request contains invalid data |

This call takes values for a lead quality, and either

1. Updates the values for that lead quality \(after  you have provided an id in the parameters\), or
2. Adds the lead quality to the system \(if the id parameter is missing\) 1. The result of this call will contain the status of the result \(either

   true or false\) and the lead quality identifier of the updated or newly

   created lead quality.

