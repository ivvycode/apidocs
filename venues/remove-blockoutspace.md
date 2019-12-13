# Remove Blockout Space

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=removeBlockoutSpace" %}
{% api-method-summary %}
Remove Blockout Space
{% endapi-method-summary %}

{% api-method-description %}
Remove blockout space from a function diary
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the blockout space belongs
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="integer" required=true %}
The unique id of the blockout space to remove
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Successfully removing an blockout space from a function diary.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "errorType": null
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

| Code | Description |
| :--- | :--- |
| 1 | Unknown error |
| Specific Code: 24274 | The blockout space could not be found |

