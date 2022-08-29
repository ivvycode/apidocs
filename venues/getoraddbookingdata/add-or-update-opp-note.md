# Add or Update Note

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=addOrUpdateOpportunityNote" method="post" summary="Add or Update Note which belongs opportunity" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the note
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the note belongs
{% endswagger-parameter %}

{% swagger-parameter name="leadId" type="integer" in="path" %}
The unique id of the lead to which the note belongs
{% endswagger-parameter %}

{% swagger-parameter name="note" type="string" in="path" %}
The description of the note.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true,
  "id": 755
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

### Add Note

```javascript
{
  "venueId": 1,
  "leadId": 10,
  "note": "test note",
}
```

### Update Note

```javascript
{
  "id": 3269,
  "venueId": 1,
  "leadId": 10,
  "note": "test note",
}
```

## Returns

| Property | Description                               |
| -------- | ----------------------------------------- |
| success  | Whether or not the note was added/updated |
| id       | The unique id of the note                 |

## Throws

| Code                 | Description |
| -------------------- | --------------------------------------------- |
| Specific Code: 24438 | The venue does not exist |
| Specific Code: 24441 | The lead/opportunity does not exist |
| Specific Code: 24434 | The note does not exist  |
| Specific Code: 24435 | An error has occured  |
| Specific Code: 24436 | The request contains invalid |
| Specific Code: 24437 | Invalid Data  |