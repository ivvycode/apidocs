# Add or Update Blockout Space

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="venue?action=addOrUpdateSpaceBlockout" %}
{% api-method-summary %}
Add or Update Space Blockout
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

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

### Add Space Blockout

```javascript
{
  "venueId": "107",
  "name": "Space Blockout API",
  "spaceId": 1,
  "startDateTime": "2018-03-05 03:00:00 UTC",
  "endDateTime": "2018-03-05 06:00:00 UTC",
}
```

### Update Space Blockout

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
| success | Whether or not the Space Blockout was added to the venue |
| id | The unique id of the Space Blockout |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24270 | The request is empty |
| Specific Code: 24271 | The Space Blockout does not exist |
| Specific Code: 24272 | The Space Blockout details are invalid |
| Specific Code: 24273 | An unknown error has occurred |

This call takes values for a Space Blockout, and either

1. Updates the values for that Space Blockout \(after you have provided an id in the parameters\), or
2. Adds the Space Blockout to the system \(if the id parameter is missing\)
   1. The result of this call will contain the status of the result \(either true or false\) and the Space Blockout identifier of the updated or newly created Space Blockout.

