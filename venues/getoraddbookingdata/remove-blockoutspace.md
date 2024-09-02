# Remove Blockout Space

{% swagger baseUrl="[PlatformAddress]" path="/api/1.0/" path="venue?action=removeSpaceBlockout" method="post" summary="Remove Blockout Space" %}
{% swagger-description %}
Remove a blockout space from a function diary
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the blockout space belongs
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="body" %}
The unique id of the blockout space to remove
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
  "success": true,
  "errorType": null
}
```
{% endswagger-response %}
{% endswagger %}

| Code                 | Description                           |
| -------------------- | ------------------------------------- |
| 1                    | Unknown error                         |
| Specific Code: 24274 | The blockout space could not be found |
