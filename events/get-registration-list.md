# Get Registration List

### Description

Get list of registration.

### API URL

`[PlatformAddress]/api/1.0/event?action=getRegistrationList`

### Parameters

| Property | Description | Type |
| --- | --- | --- |
| perPage | The number of registrations to get in a single api call | Must be an integer greater than 0 and maximum 100 |
| start | The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\) | Must be an integer 0 or greater |
| eventId | The event identifier | Must be a Integer |

### Additional [Filter ](../interpreting-the-response/filtering.md)Properties

| Property | Description | Type |
| --- | --- | --- |
| modifiedDate | Filter by modified date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |

### Returns

A collection object with the following properties in the results

| Property | Description |
| --- | --- |
| id | The unique registration identifier |
| currentStatus | The current status of the event |
| isExhibitor | Whether or not event registration is exhibitor |
| completedDate | The registered date time of event registration |
| mainContactId | The main contact id of event registration |
| firstName | The first name of the event registration |
| lastName | The last name of the event registration |
| phone | The phone number of event registration |
| invoiceTotalCost | The total cost of event registration |
| invoiceTotalPaid | The total amount paid of event registration |
| modifiedDate | The date & time the registration was last modified |

The result from this call will be a collection of all the events the user has access to. This call also accepts the pagination and filter properties.

The result from this call will be a [collection](./#collections) of all the events the user has access to. This call also accepts the [pagination](./#pagination) and [filter](./#filtering) properties.

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24206 | Unable to find event |

