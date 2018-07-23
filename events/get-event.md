# Get Event

### Description

Add or update event details.

### API URL

`[PlatformAddress]/api/1.0/event?action=getEvent`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The event identifier | Required | integer |

### Returns

| Property | Description |
| --- | --- |
| id | The unique event identifier |
| code | The code for the event |
| title | The title of the event |
| domainName | The domain name of the event |
| startDateTime | The start of the event, at UTC |
| endDateTime | The end of the event, at UTC |
| numRegistered | The number of registrations |
| currentStatus | The current status of the event |
| appTitle | The title to display on mobile platforms |
| twitter | Twitter hashtag for this event |
| appBanner | Banner to display on mobile platforms |
| map | Map of the event |
| includeSpeakers | Whether or not the event includes speakers |
| displaySpeakers | Whether or not the speakers are displayed on the event website |
| includeSponsors | Whether or not the event includes sponsors |
| displaySponsors | Whether or not there are sponsors displayed on the event website |
| includeBooths | Whether or not the event includes exhibition booths |
| displayExhibitors | Whether or not there are exhibitors displayed on the event website |
| includeAbstracts | Whether or not the event includes abstracts |
| displayAbstracts | Whether or not there are abstracts displayed on the event website |
| includeHotels | Whether or not the event includes hotel accommodation |
| includeTravel | Whether or not the event includes travel \(flights and transfers\) |
| includeMembership | Whether or not the event includes memberships |
| eventTags | The tags of the event |

### Event tags

| Code | Description |
| --- | --- |
| id | The unique identifier for the event tag |
| name | The name of the event tag |

### Throws

| Property | Description |
| --- | --- |
| Specific Code: 24097 | Unable to find event |

The event identifier must be provided as part of this call to fetch the specific event. E.g. {"id":1} can be used to fetch the details of an event with the identifier of 1.

