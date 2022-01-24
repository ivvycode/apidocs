# Add or Update Guest Room

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=addOrUpdateGuestRoom" method="post" summary="Add or Update Guest Room" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the guest room
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the rate plan belongs
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name of the venue room
{% endswagger-parameter %}

{% swagger-parameter name="code" type="string" in="path" %}
The unique code assigned to the room
{% endswagger-parameter %}

{% swagger-parameter name="categoryIds" type="array" in="path" %}
An array of category ids to which the room belongs.
{% endswagger-parameter %}

{% swagger-parameter name="capacity" type="integer" in="path" %}
The total number of this room type at the venue.
{% endswagger-parameter %}

{% swagger-parameter name="description" type="string" in="path" %}
A html formatted description of the room.
{% endswagger-parameter %}

{% swagger-parameter name="numStandardAdults" type="integer" in="path" %}
The number of standard adults allowed in the room.
{% endswagger-parameter %}

{% swagger-parameter name="numExtraAdults" type="integer" in="path" %}
The number of standard adults allowed in the room.
{% endswagger-parameter %}

{% swagger-parameter name="extraAdultCost" type="number" in="path" %}
The price of adding an extra adult to the room.
{% endswagger-parameter %}

{% swagger-parameter name="canSmoke" type="bool" in="path" %}
Whether or not smoking is allowed in the room.
{% endswagger-parameter %}

{% swagger-parameter name="active" type="bool" in="path" %}
Whether or not venue room is active on marketplace.
{% endswagger-parameter %}

{% swagger-parameter name="marketplaceName" type="bool" in="path" %}
Whether or not venue room is active on marketplace.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true,
  "id": 10
}
```
{% endswagger-response %}
{% endswagger %}

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

| Property | Description                                              |
| -------- | -------------------------------------------------------- |
| success  | Whether or not the Space Blockout was added to the venue |
| id       | The unique id of the Space Blockout                      |

## Throws

| Code                 | Description                       |
| -------------------- | --------------------------------- |
| Specific Code: 24312 | The room does not exist           |
| Specific Code: 24313 | An error has occurred             |
| Specific Code: 24314 | The request contains invalid data |
| Specific Code: 24315 | An unknown error has occurred     |
