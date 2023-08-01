# Add or Update Contact Note

{% swagger baseUrl="[PlatformAddress]/api/1.0/contact?action=addOrUpdateContactNote" method="post" summary="Add or Update Contact Note" %}
{% swagger-description %}
Add or update contact note details
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="body" %}
The contact note's identifier. (Leave empty to add new)
{% endswagger-parameter %}

{% swagger-parameter name="contactId" type="integer" in="body" %}
The unique identifier of the contact to which note belongs
{% endswagger-parameter %}

{% swagger-parameter name="noteText" type="string" in="body" %}
The discription of the note
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

## Example Request: Adding a contact note

```javascript
{
    "contactId": 2,
    "noteText": "test note",
}
```

## Returns

| Property | Description                                      |
| -------- | ------------------------------------------------ |
| success  | If the contact note was successfully added or updated |
| id       | The unique identifier for the contact note           |
