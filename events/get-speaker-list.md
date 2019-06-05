# Get Speaker List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/event?action=getSpeakerList" path="" %}
{% api-method-summary %}
Get Speaker List
{% endapi-method-summary %}

{% api-method-description %}
Get the list of speakers at an event
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="event" type="integer" required=true %}
The event identifier
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Example: Fetch the list of speakers at an event`

```javascript
{ 
  "event":15593
}
```

## Returns

A collection object with the following properties of objects in the results

| Property | Description |
| :--- | :--- |
| id | The unique speaker identifier |
| fullName | The speaker’s name |
| organisation | The speaker’s organisation |
| position | The position of the speaker |
| profileDescription | The speaker’s profile |
| profileImageUrl | The URL to the speaker’s profile image |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24124 | Event does not have speakers |
| Specific Code: 24101 | Unable to find event |

