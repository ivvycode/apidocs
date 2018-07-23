# Get Email Log List

### Description

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

### Api Url

`[PlatformAddress]/api/1.0/account?action=getEmailLogList`

### Returns

| Property | Description |
| --- | --- |
| id | The unique identifier of the email |
| contactId | The contact id of of the email |
| userId | The user id of of the email |
| eventId | The event id of of the email |
| type | The type of of the email |
| refType | The reference type id of of the email |
| refId | The reference id of of the email |
| from | The from address of of the email |
| to | The to address of the email |
| bcc | The bcc of the email |
| subject | The subject of the email |
| body | The body of the email |
| sentTime | The sent time of the email in UTC |
| success | Whether or not email has been sent or not |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24151 | Account does not exist |

### Example Response

`Example: Get a specific account’s Email Logs List`

```javascript
{
  "meta": {
    "totalResults": 1,
    "start": 0,
    "perPage": 100,
    "count": 1
  },
  "results": [
    {
      "id": 2,
      "contactId": 25943,
      "userId": null,
      "eventId": 50,
      "type": 1,
      "refType": 5,
      "refId": 184133,
      "from": "5U2ZD@V5P7T.com",
      "to": "8X2PEZ@FF1UAL.com",
      "bcc": null,
      "subject": "CCWXL3A8",
      "body": "3N5RU3V5",
      "sentTime": "2013-07-04 07:18:29 UTC",
      "success": true
    }
  ]
}
```

### refType:

One of the following values:

* 0 = Other
* 1 = Contact
* 2 = Event
* 3 = Membership
* 4 = Abstract
* 5 = Registration
* 6 = Invoice
* 7 = Author
* 8 = Task
* 9 = Credit Note
* 10 = Survey
* 11 = Venue Marketplace
* 12 = Booking
* 13 = Company
* 14 = Floor Plan

### type:

One of the following values:

* 0 = Unknown
* 1 = Completed Event Registration
* 2 = Completed Event Registration \(Waiting on Payment\)
* 3 = Accommodation Confirmation
* 4 = Travel Confirmation
* 5 = Registration Payment Reminder
* 8 = Exhibitor Final Confirmation
* 11 = Abstract/Paper Submission Created
* 12 = Abstract/Paper Changes Requested
* 13 = Abstract/Paper Submission Rejected
* 14 = Abstract/Paper Submission Accepted
* 15 = Abstract/Paper Reviewer Added
* 16 = Contact Changed
* 17 = Hotel Changed
* 18 = Flight Changed
* 19 = Tickets Changed
* 20 = Exhibitor Confirmation
* 21 = Session Confirmation
* 22 = Session Changed
* 23 = Abstract Changed
* 24 = Final Confirmation
* 30 = Event Feedback
* 31 = Event Reminder
* 26 = Abstract
* 27 = API Leadtracker
* 28 = Contact Subscribed
* 29 = Transfer Changed
* 32 = Incomplete Registration
* 1000 = Password Reset
* 1001 = Notification
* 1002 = Task
* 1500 = Statement
* 1501 = Invoice
* 1502 = Credit Note
* 2000 = Membership Signup
* 2001 = Membership Renewal
* 2002 = Renewal Notice
* 3000 = Survey
* 1003 = New Company Added
* 4000 = Venue Booking Document
* 4001 = Venue Booking Floor Plan

