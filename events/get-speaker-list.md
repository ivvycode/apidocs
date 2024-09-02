# Get Speaker List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="event?action=getSpeakerList" method="post" summary="Get Speaker List" %}
{% swagger-description %}
Get the list of speakers at an event
{% endswagger-description %}

{% swagger-parameter name="event" type="integer" in="path" %}
The event identifier
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "meta":{
    "totalResults":1,
    "start":0,
    "perPage":1,
    "count":1
    },
  "results":
  [
    {
      "id":"6",
      "fullName":"Mr Speaker",
      "organisation":"Google",
      "position":"Lead Developer",
      "profileDescription":"...",
      "profileImageUrl":"https://…./8869de9237bb1.png"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Example: Fetch the list of speakers at an event`

```javascript
{
  "event":15593
}
```

## Returns

A collection object with the following properties of objects in the results

| Property           | Description                            |
| ------------------ | -------------------------------------- |
| id                 | The unique speaker identifier          |
| fullName           | The speaker’s name                     |
| organisation       | The speaker’s organisation             |
| position           | The position of the speaker            |
| profileDescription | The speaker’s profile                  |
| profileImageUrl    | The URL to the speaker’s profile image |

## Throws

| Code                 | Description                  |
| -------------------- | ---------------------------- |
| Specific Code: 24124 | Event does not have speakers |
| Specific Code: 24101 | Unable to find event         |
