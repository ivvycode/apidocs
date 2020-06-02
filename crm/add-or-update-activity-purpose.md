# Add or Update Activity Purpose

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=addOrUpdateActivityPurpose" path="" %}
{% api-method-summary %}
Add or Update Activity Purpose
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the activity purpose
\(Leave empty if adding a new activity purpose\)
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
The name of the event activity purpose
\(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="integer" required=false %}
The [type](add-or-update-activity-purpose.md#activity-purpose-type) of the event activity purpose
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

## Activity Purpose Type

| Id | Name |
| :--- | :--- |
| 1 | Account |
| 2 | Function |
| 3 | Corporate |
| 4 | Group |

## Example Request

### Add Activity Purpose

```javascript
{
  "name": "Purpose 1",
  "type": "1",
}
```

### Update Activity Purpose

```javascript
{
  "id": 755,
  "name": "Updated Purpose"
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the activity purpose was added |
| id | The unique id of the activity purpose |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24300 | The event activity purpose does not exist |
| Specific Code: 24301 | An error has occurred |
| Specific Code: 24302 | The request contains invalid data |
| Specific Code: 24303 | The request contains invalid data |

This call takes values for a activity purpose, and either

1. Updates the values for that activity purpose \(after  you have provided an id in the parameters\), or
2. Adds the activity purpose to the system \(if the id parameter is missing\) 1. The result of this call will contain the status of the result \(either

   true or false\) and the activity purpose identifier of the updated or newly

   created activity purpose.

