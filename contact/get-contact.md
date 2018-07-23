# Get Contact

### Description

Get the contact details.

### API URL

`[PlatformAddress]/api/1.0/contact?action=getContact`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The contacts identifier | Required | integer |
| useEventSortOrder | If true, the eventInvitations and eventRegistrations will be returned ordered by the Event Start Date | Required | boolean |

### Returns

| Property | Description |
| --- | --- |
| id | The unique identifier for the contact |
| firstName | The contact’s first name |
| lastName | The contact’s last name |
| email | The contact’s email address |
| phone | The contact’s phone number |
| status | The contact's [email status](get-contact.md#email-status) |
| smsStatus | The contact’s [sms status](get-contact.md#sms-status) |
| customFields | The custom field information for the contact. This is an array of fields, each an object with the [keys](get-contact.md#keys). |
| groups | The subscription group information for the contact. |
| companies | This will an array company ids to which the contact belongs. |
| externalId | This will be an external id of the contact |
| modifiedDate | The modified date of the contact |
| eventInvitations | An array of events the contact has been invited to. Each element of the array is an object with [the event invitations fields](get-contact.md#event-invitations) |
| eventRegistrations | An array of events the contact has registered for. Each element of the array is an object with [the event registration fields](get-contact.md#event-registrations-details). |

### Email status

| \# | Description |
| --- | --- |
| 1 | Subscribed |
| 2 | Unsubscribed |
| 3 | Bounced |
| 4 | Registering |
| 5 | No Marketing |

### Sms status

| \# | Description |
| --- | --- |
| 1 | Subscribed |
| 2 | Unsubscribed |
| 3 | Failed |
| 4 | No Marketing |

### Keys

| Keys |
| --- |
| fieldId |
| displayName |
| value |

### Event Invitations

| Property | Description |
| --- | --- |
| eventId | The event identifier of the invitation |
| eventCode | The code of the event of the invitation |
| eventStartDateTime | The timestamp the event is starting |
| inviteLinkYes | Invitation link for the Yes response for this contact to the event |
| inviteLinkNo | Invitation link for No response for this contact to the event |
| response | The contacts response to the invitation. [List of response values](get-contact.md#response-values). |

### Response values

| \# | Description |
| --- | --- |
| U | Undecided |
| Y | Yes |
| N | No |

### Event Registrations Details

| Property | Description |
| --- | --- |
| eventId | The event identifier of the registration |
| eventCode | The code of the event of the registration |
| eventStartDateTime | The timestamp the event is starting |
| registrationId | The unique identifier of the registration |
| currentStatus | [The status of the registration](get-contact.md#registration-status) |
| confirmedDate | Timestamp of the date the registration was confirmed |
| isPaymentWaiting | If the registration is payment waiting or not |
| printTicketUrl | The URL the registrations tickets |
| printTicketUrlPdf | Link to the PDF for the registrations tickets |
| attendeeCount | Total number of attendees for this registration |
| invoiceUrl | The URL for the registration primary invoice |
| invoiceUrlPdf | Link to the PDF for the registration primary invoice |
| guestDetails | An array of objects with [the guest details.](get-contact.md#guest-details) |
| invoices | The list of invoices associated with the registration. Each element of the array is an object with [the invoice fields.](get-contact.md#invoice-details) |

### Registration Status

| \# | Description |
| --- | --- |
| 2 | Completed |
| 3 | Cancelled |
| 4 | Payment Required |

### Guest Details

| Property | Description |
| --- | --- |
| contactId | The identifier for the contact if known |
| fullName | Name of guest |
| email | Email address of guest |
| attended | If the contact has attended the event |
| attendedDateTime | When the contact attended the event |

### Invoice Details

| Property | Description |
| --- | --- |
| id | The unique identifier for the invoice |
| reference | The reference number of the invoice |
| title | The title of the invoice |
| currentStatus | The current status of the invoice. The value of this field will be [one of the following current status](get-contact.md#invoice-current-status). |
| description | The description of the invoice |
| currency | The currency of the values of this invoice |
| totalCost | The total amount of the invoice |
| totalPaid | How much has been paid off the invoice |
| invoiceUrl | The URL for the invoice |
| invoiceUrlPdf | The URL for the invoice pdf |

### Invoice current status

| \# | Description |
| --- | --- |
| 0 | Not Paid |
| 1 | Unconfirmed Paid |
| 2 | Written Off |
| 3 | Failed |
| 4 | Cancelled |
| 5 | Refunded |

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24096 | Unable to find contact |

The contact identifier must be provided to fetch a specific contact from the system.

### Example Request

`Get a specific contact`

```javascript
{ 
  "id":6
}
```

### Example Response

```javascript
{
    "id":"25146",
    "firstName":"Test",
    "lastName":"User",
    "email":"user@test.com",
    "phone":"0455550000",
    "customFields":[
        {"fieldId":"102","displayName":"Dietary Requirements","value":[""]},
        {"fieldId":"103","displayName":"Shirt Size","value":["Medium"]}
    ],
    "groups":[
        {"contactId":"25146","groupId":"2481","joinDate":"2012-04-16 21:07:04"},
        {"contactId":"25146","groupId":"2485","joinDate":"2014-05-6 12:32:12"}
    ],
    "companies":[
        4,5,6
    ],
    "externalId":"59fc43b6726be"
}
```

