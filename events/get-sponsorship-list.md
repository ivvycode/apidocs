# Get Sponsorship List

### Description

Get sponsorship list.

### API URL

`[PlatformAddress]/api/1.0/event?action=getSponsorshipList`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| event | The event identifier | Required | integer |

### Returns

A collection array with the following object properties in the results

| Property | Description |
| --- | --- |
| id | The unique sponsor identifier |
| name | The name of the sponsor |
| description | The description of the sponsor |
| websiteAddress | The URL to the sponsor details |
| logoImageUrl | The URL to the sponsor details |
| level | The sponsorship level of the sponsor |
| customLevelId | The custom level identifier if this sponsor has a custom level assigned to it |
| sponsorshipAmount | How much this sponsorship is for |
| sponsorshipAmountPaid | How much has been paid by the sponsor so far |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24094 | Event does not have sponsors |
| Specific Code: 24100 | Unable to find event |

Lists the sponsors that are sponsoring the event.

`Example: Fetch the list of sponsors on an event`

### Example Request

```javascript
{
  "event":15593
}
```

### Example Response

```javascript
{
"meta":{"totalResults":1,"start":0,"perPage":1,"count":1},"results":[{"id":"1","name":"Test Sponsor for event 1","description":"...","websiteAddress":"www.sponsor1.com","logoI
mageUrl":"https://.../554ac739bcc9a.png","level":"9","customLevelId":null,"sponsorshipAmount":"44","sponsorshipAmountPaid":"4"}]
}
```

