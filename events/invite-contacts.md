# Invite Contacts

### Description

Invite contact\(s\) to event.

### API URL

`[PlatformAddress]/api/1.0/event?action=inviteContacts`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| event | The event identifier to invite the contact to | Required | integer. |
| contacts | An array of contact identifiers to invite to the event | Required | array of integers |

### Returns

| Property | Description |
| --- | --- |
| results | An array of objects with the following properties |
| contact | The contact identifier |
| status | The status of the request |
| inviteLinkYes | Invitation link for the YES responses |
| inviteLinkNo | Invitation link fo the NO responses |

To invite a contact to the event, pass through the event identifier and an array of contact identifiers through to this call. The result will be a an array indicating if each of the contacts invitation was successful or not, and if so the links for responding to the invitations for both yes and no.

`Example: Invite contacts with identifiers 1, 2 and 3 to event with the identifier 4`

### Example Request

```javascript
{
  "event":4,
  "contacts":[1,2,3]
}
```

### Example Response

```javascript
{
    "results":[
        {
            "contact":1,
            "status":true,
            "inviteLinkYes":"http://....",
            "inviteLinkNo":"http://...."
        },
        {   "contact":2,
            "status":false},
        {
            "contact":3,
            "status":true
            "inviteLinkYes":"http://....",
            "inviteLinkNo":"http://...."
        }
    ]
}
```

