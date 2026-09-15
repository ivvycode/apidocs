# Add or Update Company Note

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="contact?action=addOrUpdateCompanyNote" method="post" summary="Add or Update Company Note" %}
{% swagger-description %}
Add or update company note details
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="body" %}
The company note's identifier. (Leave empty to add new)
{% endswagger-parameter %}

{% swagger-parameter name="companyId" type="integer" in="body" %}
The unique identifier of the company to which note being added/updated
{% endswagger-parameter %}

{% swagger-parameter name="noteText" type="string" in="body" %}
The description of the note
{% endswagger-parameter %}


{% swagger-response status="200" description="" %}
```
{
  "success": true
  "id":33884
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request: Adding a company note

```javascript
{
    "companyId": 2,
    "noteText": "test note",
}
```

## Returns

| Property | Description                                      |
| -------- | ------------------------------------------------ |
| success  | If the company note was successfully added or updated |
| id       | The unique identifier for the company note           |
