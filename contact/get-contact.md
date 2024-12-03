# Get Contact

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="contact?action=getContact" method="post" summary="Get Contact" %}
{% swagger-description %}
Get the contact details
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The contact's identifier
{% endswagger-parameter %}

{% swagger-parameter name="useEventSortOrder" type="boolean" in="path" %}
If true, the eventInvitations and eventRegistrations will be returned ordered by Event Start Date
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
    "id": 7427530,
    "firstName": "Test",
    "lastName": "User",
    "email": "user@test.com",
    "phone": "0455550000",
    "status": 1,
    "smsStatus": 1,
    "customFields": [],
    "groups": [
        {
            "contactId": 7427530,
            "groupId": 57138,
            "joinDate": "2018-09-07 02:11:47"
        }
    ],
    "companies": [4, 5, 6],
    "companiesData":[
        {"id":4,"businessName":"Company Name 1"},
        {"id":5,"businessName":"Company Name 3 (Department)"},
        {"id":6,"businessName":"Company Name 2"},
    ],
    "externalId": null,
    "modifiedDate": "2018-09-07 02:11:47 UTC",
    "isAnonymised": false,
    "eventInvitations": [],
    "eventRegistrations": []
}
```
{% endswagger-response %}
{% endswagger %}

### Example Request

This example request will obtain the details of the contact with the id "6"

```javascript
{
  "id":6
}
```

## Returns

|                    |                                                                                                                                                                             |          |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| **Property**       | **Description**                                                                                                                                                             | **Type** |
| id                 | The unique identifier for the contact                                                                                                                                       | integer  |
| firstName          | The contact’s first name                                                                                                                                                    | string   |
| lastName           | The contact’s last name                                                                                                                                                     | string   |
| email              | The contact’s email address                                                                                                                                                 | string   |
| phone              | The contact’s phone number                                                                                                                                                  | integer  |
| status             | The contact's [email status](get-contact.md#email-status)                                                                                                                   | enum     |
| smsStatus          | The contact’s [sms status](get-contact.md#sms-status)                                                                                                                       | enum     |
| customFields       | The custom field information for the contact. This is an array of fields, each an object with the [keys](get-contact.md#custom-fields-keys).                                              | array    |
| groups             | The subscription group information for the contact.                                                                                                                         | array    |
| companies          | This will an array company ids to which the contact belongs.                                                                                                                | array    |
| companiesData      | This will an array company containing id and businessName for each company to which the contact belongs.                                                                    | array    |
| externalId         | This will be an external id of the contact                                                                                                                                  | integer  |
| modifiedDate       | The modified date of the contact                                                                                                                                            | date     |
| isAnonymised       | Whether or not contact data is annonymised                                                                                                                                  | boolean  |
| eventInvitations   | An array of events the contact has been invited to. Each element of the array is an object with [the event invitations fields](get-contact.md#event-invitations)            | array    |
| eventRegistrations | An array of events the contact has registered for. Each element of the array is an object with [the event registration fields](get-contact.md#event-registrations-details). | array    |
| externalUrls | This is an array of [ExternalUrl](get-contact.md#external-url-field) field objects of the contact. | array    |
| privacyConsentData | The object of [Privacy Consent](get-contact.md#privacy-consent-data) field objects of the contact. | array    |

### Status Options - Email Registration Status

The status is the record of whether the contact has opted in to email communication.

|       |                 |
| ----- | --------------- |
| **#** | **Description** |
| 1     | Subscribed      |
| 2     | Unsubscribed    |
| 3     | Bounced         |
| 4     | Registering     |
| 5     | No Marketing    |

### Sms status

The sms status is the record of whether the contact has opted in to sms communication.

|       |                 |
| ----- | --------------- |
| **#** | **Description** |
| 1     | Subscribed      |
| 2     | Unsubscribed    |
| 3     | Failed          |
| 4     | No Marketing    |

### Custom Fields Keys

|             |
| ----------- |
| **Keys**    |
| fieldId     |
| displayName |
| value       |

### Event Invitations

|                    |                                                                                                     |
| ------------------ | --------------------------------------------------------------------------------------------------- |
| **Property**       | **Description**                                                                                     |
| eventId            | The event identifier of the invitation                                                              |
| eventCode          | The code of the event of the invitation                                                             |
| eventStartDateTime | The timestamp the event is starting                                                                 |
| inviteLinkYes      | Invitation link for the Yes response for this contact to the event                                  |
| inviteLinkNo       | Invitation link for No response for this contact to the event                                       |
| response           | The contacts response to the invitation. [List of response values](get-contact.md#response-values). |

#### Event Invitations Response values

|       |                 |
| ----- | --------------- |
| **#** | **Description** |
| U     | Undecided       |
| Y     | Yes             |
| N     | No              |

### Event Registrations Details

|                    |                                                                                                                                                          |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Property**       | **Description**                                                                                                                                          |
| eventId            | The event identifier of the registration                                                                                                                 |
| eventCode          | The code of the event of the registration                                                                                                                |
| eventStartDateTime | The timestamp the event is starting                                                                                                                      |
| registrationId     | The unique identifier of the registration                                                                                                                |
| currentStatus      | [The status of the registration](get-contact.md#registration-status)                                                                                     |
| confirmedDate      | Timestamp of the date the registration was confirmed                                                                                                     |
| isPaymentWaiting   | If the registration is payment waiting or not                                                                                                            |
| printTicketUrl     | The URL the registrations tickets                                                                                                                        |
| printTicketUrlPdf  | Link to the PDF for the registrations tickets                                                                                                            |
| attendeeCount      | Total number of attendees for this registration                                                                                                          |
| invoiceUrl         | The URL for the registration primary invoice                                                                                                             |
| invoiceUrlPdf      | Link to the PDF for the registration primary invoice                                                                                                     |
| guestDetails       | An array of objects with [the guest details.](get-contact.md#guest-details)                                                                              |
| invoices           | The list of invoices associated with the registration. Each element of the array is an object with [the invoice fields.](get-contact.md#invoice-details) |

#### Event Registration Status (currentStatus)

|       |                  |
| ----- | ---------------- |
| **#** | **Description**  |
| 2     | Completed        |
| 3     | Cancelled        |
| 4     | Payment Required |

#### Guest Details

|                  |                                         |
| ---------------- | --------------------------------------- |
| **Property**     | **Description**                         |
| contactId        | The identifier for the contact if known |
| fullName         | Name of guest                           |
| email            | Email address of guest                  |
| attended         | If the contact has attended the event   |
| attendedDateTime | When the contact attended the event     |

### Invoice Details

|               |                                                                                                                                                  |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Property**  | **Description**                                                                                                                                  |
| id            | The unique identifier for the invoice                                                                                                            |
| reference     | The reference number of the invoice                                                                                                              |
| title         | The title of the invoice                                                                                                                         |
| currentStatus | The current status of the invoice. The value of this field will be [one of the following current status](get-contact.md#invoice-current-status). |
| description   | The description of the invoice                                                                                                                   |
| currency      | The currency of the values of this invoice                                                                                                       |
| totalCost     | The total amount of the invoice                                                                                                                  |
| totalPaid     | How much has been paid off the invoice                                                                                                           |
| invoiceUrl    | The URL for the invoice                                                                                                                          |
| invoiceUrlPdf | The URL for the invoice pdf                                                                                                                      |

#### Invoice current status

|       |                  |
| ----- | ---------------- |
| **#** | **Description**  |
| 0     | Not Paid         |
| 1     | Unconfirmed Paid |
| 2     | Written Off      |
| 3     | Failed           |
| 4     | Cancelled        |
| 5     | Refunded         |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## External URL Field

An External URL field is an object with the following details.

| Property | Type   | Description                                                                                                                                              |
| -------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ref      | string | The unique reference key of the external URL                                                                                                             |
| url      | string | The url link (https) scheme eg. https://example.com                                                                                                      |
| label    | string | The label of the URL to display.                                                                                                                         |

## Privacy Consent Data


| Property | Description |
| -------- | ------------ |
| source | The [source](get-contact.md#source) of the consent  |
| dateTime | The date time when the consent given |

## Source

| Source | Description |
| -------- | ------------ |
| 1 | User Initiated Entry  |
| 2 | Marketplace |
| 3 | Website Booking Engine |
| 4 | Event Website |
| 5 | API |


## Throws

|                      |                        |
| -------------------- | ---------------------- |
| **Code**             | **Description**        |
| Specific Code: 24096 | Unable to find contact |

The contact identifier must be provided to fetch a specific contact from the system.
