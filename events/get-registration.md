# Get Registration

### Description

Get registration details.

### API URL

`[PlatformAddress]/api/1.0/event?action=getRegistration`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The registration identifier | Required | integer |
| eventId | The event identifier to which registration belongs | Required | integer |

### Returns

| Property | Description |
| --- | --- |
| id | The unique registration identifier |
| currentStatus | The current status of the event |
| isExhibitor | Whether or not event registration is exhibitor |
| completedDate | The registered date time of event registration |
| firstName | The first name of the event registration |
| lastName | The last name of the event registration |
| phone | The phone number of event registration |
| modifiedDate | The date & time the registration was last modified |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24207 | Unable to find event |
| Specific Code: 24208 | Invalid Registration Id |
| Specific Code: 24209 | Registration not found |

