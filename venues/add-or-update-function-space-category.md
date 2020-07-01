# Add or Update Venue Space Category
# Add or Update Venue Space Category

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateFunctionSpaceCategory" path="" %}
{% api-method-summary %}
Add or Update Venue Space Category
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}

{% api-method-parameter name="venueId" type="integer" required=true %}

{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the space category
\(Leave empty if adding a new space category\)
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
The name of the event space category
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
  "id": 7
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

### Add space category

```javascript
{
  "venueId": "1",
  "name": "Category 1",
}
```

### Update space category

```javascript
{
  "id": 7,
  "name": "Updated Category"
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the space category was added |
| id | The unique id of the space category |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24308 | The venue space category does not exist |
| Specific Code: 24309 | An error has occurred |
| Specific Code: 24310 | The request contains invalid data |
| Specific Code: 24311 | The request contains invalid data |

This call takes values for a space category, and either

1. Updates the values for that space category \(after  you have provided an id in the parameters\), or
2. Adds the space category to the system \(if the id parameter is missing\) 1. The result of this call will contain the status of the result \(either

   true or false\) and the space category identifier of the updated or newly

   created space category.

