# Add or Update Guest Room

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateGuestRoom" path="" %}
{% api-method-summary %}
Add or Update Guest Room
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}

{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the guest room
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the rate plan belongs
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
The name of the venue room
{% endapi-method-parameter %}

{% api-method-parameter name="code" type="string" required=true %}
The unique code assigned to the room
{% endapi-method-parameter %}

{% api-method-parameter name="categoryIds" type="array" required=false %}
An array of category ids to which the room belongs.
{% endapi-method-parameter %}

{% api-method-parameter name="capacity" type="integer" required=true %}
The total number of this room type at the venue.
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=true %}
A html formatted description of the room.
{% endapi-method-parameter %}

{% api-method-parameter name="numStandardAdults" type="integer" required=true %}
The number of standard adults allowed in the room.
{% endapi-method-parameter %}

{% api-method-parameter name="numExtraAdults" type="integer" required=true %}
The number of standard adults allowed in the room.
{% endapi-method-parameter %}

{% api-method-parameter name="extraAdultCost" type="number" required=true %}
The price of adding an extra adult to the room.
{% endapi-method-parameter %}

{% api-method-parameter name="canSmoke" type="bool" required=true %}
Whether or not smoking is allowed in the room.
{% endapi-method-parameter %}

{% api-method-parameter name="active" type="bool" required=true %}
Whether or not venue room is active on marketplace.
{% endapi-method-parameter %}

{% api-method-parameter name="marketplaceName" type="bool" required=true %}
Whether or not venue room is active on marketplace.
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
