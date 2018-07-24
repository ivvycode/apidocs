# Get Speaker List

### Description

Get the list of speakers at an event

### API URL

`[PlatformAddress]/api/1.0/event?action=getSpeakerList`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| event | The event identifier | Required | integer |

### Returns

A collection object with the following properties of objects in the results

| Property | Description |
| --- | --- |
| id | The unique speaker identifier |
| fullName | The speaker’s name |
| organisation | The speaker’s organisation |
| position | The position of the speaker |
| profileDescription | The speaker’s profile |
| profileImageUrl | The URL to the speaker’s profile image |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24124 | Event does not have speakers |
| Specific Code: 24101 | Unable to find event |

Lists the speakers of the event.

`Example: Fetch the list of speakers at an event`

### Example Request

```javascript
{ 
  "event":15593
}
```

### Example Response

```javascript
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

