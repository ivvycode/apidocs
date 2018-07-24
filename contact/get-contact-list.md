# Get Contact List

### Description

Get the list of contact.

### API URL

`[PlatformAddress]/api/1.0/contact?action=getContactList`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| perPage | The number of events to get in a single api call | Required | integer |
| start | The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\) | Required | integer |

### Additional [Filter](../interpreting-the-response/filtering.md) Properties

| Property | Description | Type |
| --- | --- | --- |
| fromModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| toModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |

### Returns

| Property | Description |
| --- | --- |
| id | The unique identifier for the contact |
| firstName | The contact’s first name |
| lastName | The contact’s last name |
| email | The contact’s email address |
| phone | The contact’s phone number |
| customFields | The custom field information for the contact. This is an array of fields, each an object with the [keys](get-contact-list.md#keys). |
| groups | The subscription group information for the contact. |
| companies | This will an array company ids to which the contact belongs. |
| externalId | This will be external id of the contact |
| modifiedDate | The modified date of the contact |

### keys

| fieldId |
| --- |
| displayName |
| value |

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

