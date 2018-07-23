# Get Attendee List

### Description

Get list of event.

### API URL

`[PlatformAddress]/api/1.0/event?action=getAttendeeList`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| perPage | The number of attendees to get in a single api call | Required | integer \(greater than 0 and maximum 100\) |
| start | The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\) | Required | integer \(0 or greater\) |
| eventId | The event identifier | Required | integer |

### Additional [Filter](../interpreting-the-response/filtering.md) Properties

No filters available

### Returns

A collection object with the following properties in the results

| Property | Description |
| --- | --- |
| id | The unique registration identifier |
| registrationStatus | The registration status of the event attendee |
| contactId | The contactId of event attendee |
| ticketTitle | The title of ticket |
| firstName | The first name of the event attendee |
| lastName | The last name of the event attendee |
| email | The email address of the event attendee |
| hasAttended | Whether attendee has attended event or not |
| sessionHasAttended | Whether attendee has attended session or not |
| isPublic | Whether event attndee is public or not |
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

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24210 | Unable to find event |

