# Add or Update Blockout Space

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=AddOrUpdateBlockoutSpace" path="" %}
{% api-method-summary %}
Add or Update Blockout Space
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
The unique identifier of Blockout Space  
\(Leave empty if adding a new Blockout Space\)
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The unique venue if of the Blockout Space
{% endapi-method-parameter %}

{% api-method-parameter name="spaceId" type="integer" required=false %}
The function space of Blockout Space
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
The name for the Blockout Space
\(Required when id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="startDateTime" type="string" required=true %}
When adding an Blockout Space. The start date & time of the Blockout Space.
{% endapi-method-parameter %}

{% api-method-parameter name="endDateTime" type="string" required=true %}
When adding an Blockout Space. The end date & time of the Blockout Space. The value must be on or after startDateTime. \(Datatype = timestamp\)
{% endapi-method-parameter %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "success": true,
  "id": 10
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

### Add Blockout Space

```javascript
{
  "venueId": "107",
  "name": "Blockout space API",
  "spaceId": 1,
  "startDateTime": "2018-03-05 03:00:00 UTC",
  "endDateTime": "2018-03-05 06:00:00 UTC",
}
```

### Update Blockout Space

```javascript
{
  "id": 10,
  "venueId": "107",
  "name": "Updated Name"
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the Blockout Space was added to the venue |
| id | The unique id of the Blockout Space |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24270 | The request is empty |
| Specific Code: 24271 | The Blockout Space does not exist |
| Specific Code: 24272 | The Blockout Space details are invalid |
| Specific Code: 24273 | An unknown error has occurred |

This call takes values for a Blockout Space, and either

1. Updates the values for that Blockout Space \(after you have provided an id in the parameters\), or
2. Adds the Blockout Space to the system \(if the id parameter is missing\)
    1. The result of this call will contain the status of the result \(either true or false\) and the Blockout Space identifier of the updated or newly created Blockout Space.

