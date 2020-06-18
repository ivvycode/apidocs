# Add or Update Guest Room

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateGuestRoom" path="" %}
{% api-method-summary %}
Add or Update Guest Room
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

### Add Guest Room

```javascript
{
  "venueId": "1",
  "name": "Room 3.3",
  "extraAdultCost": "15",
  "categoryIds": [
    1,2
  ],
  "capacity": 10,
  "description": "this is testing",
  "numStandardAdults": 5,
  "numExtraAdults": 0,
  "canSmoke": "0",
  "active": "0"
}
```

### Update Guest Room

```javascript
{
  "venueId": "1",
  "name": "Room 3.4",  
  "id": 54
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
| Specific Code: 24312 | The room does not exist |
| Specific Code: 24313 | An error has occurred |
| Specific Code: 24314 | The request contains invalid data |
| Specific Code: 24315 | An unknown error has occurred |
