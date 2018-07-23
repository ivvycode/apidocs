# Get Attendee

### Description

Get attendee details.

### API URL

`[PlatformAddress]/api/1.0/event?action=getAttendee`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The attendee identifier | Required | integer |
| eventId | The event identifier to which attendee belongs | Required | integer |

### Returns

| Property | Description |
| --- | --- |
| id | The unique registration identifier |
| registrationStatus | The registration status of the event attendee |
| contactId | The contactId of event attendee |
| registrationId | The registration id of event attendee |
| ticketTitle | The title of ticket |
| firstName | The first name of the event attendee |
| lastName | The last name of the event attendee |
| email | The email address of the event attendee |
| hasAttended | Whether attendee has attended event or not |
| sessionHasAttended | Whether attendee has attended session or not |
| isPublic | Whether event attendee is public or not |
| barcode | The barcode text of event attendee |
| barcodeUrl | The barcode url of event attendee |
| ticketUrl | The ticket url of event attendee |
| attendedDatetime | The attended date time of event attendee |
| sessionAttendedTimestamp | The session attended date time of event attendee |
| cost | The cost of ticket of event attendee |
| customFields | The array of custom fields data of event attendee with below details |

### Custom field details

| Property | Description |
| --- | --- |
| name | The name of the custom field |
| value | The value of the custom field for attendee |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24211 | Unable to find event |
| Specific Code: 24212 | Invalid Attendee Id |
| Specific Code: 24213 | Attendee not found |

