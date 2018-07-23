# Add or Update Opportunity

### Description

Add or update opportunity.

### API URL

`[PlatformAddress]/api/1.0/venue?action=addOrUpdateOpportunity`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The unique identifier of opportunity\(Leave empty to add the opportunity to the system.\) |  | integer |
| venueId | The unique venue id of opportunity | Required | integer |
| qualityId | The quality of opportunity |  | integer |
| companyId | The unique company id of opportunity | Required when lead belongs to company and id parameter is missing | integer |
| industryId | The unique industry id of opportunity | Required when lead belongs to contact and id parameter is missing | integer |
| sourceId | The unique source id of opportunity | Required when the id parameter is missing | integer |
| confirmedQuoteId | The unique confirmed quote id of opportunity |  | integer |
| confirmedQuoteStatus | The unique cancelled quote id of opportunity |  | integer |
| cancelledQuoteId | The unique cancelled quote id of opportunity |  | integer |
| lostToCompetition | The reson to lost to competition of opportunity |  |  |
| closedDate | The closed date of opportunity |  |  |
| companyLeadContactId | The unique contact id of the company contact | Required when lead belongs to company and id parameter is missing | integer |
| contactId | The unique contact id of opportunity | Required when lead belongs to contact and id parameter is missing | integer |
| name | The name for the opportunity | Required when the id parameter is missing |  |
| ownerUserId | The sales person id of opportunity |  | integer |
| typeId | The type of opportunity | Required when the id parameter is missing | integer |
| stageId | The stage of opportunity | Required when the id parameter is missing | integer |
| channel | The channel of opportunity |  | integer |
| description | The description for the opportunity |  |  |

### Returns

| Property | Description |
| --- | --- |
| success | Whether or not the opportunity was added to the venue |
| id | The unique id of the opportunity |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24221 | The request is empty |
| Specific Code: 24222 | The opportunity does not exist |
| Specific Code: 24224 | The opportunity details are invalid |

This call takes values for a opportunity, and either

1. Updates the values for that opportunity \(after you have provided an id in the parameters\), or
2. Adds the opportunity to the system \(if the id parameter is missing\) 1. The result of this call will contain the status of the result \(either

   true or false\) and the opportunity identifier of the updated or newly

   created opportunity.

### `Add opportunity`

### Example Request

```javascript
{
  "venueId": "107",
  "name": "Lead By API",
  "contactId": "918",
  "typeId": "18",
  "sourceId": "25",
  "stageId": "69",
  "industryId": "77",
  "stageReasonId": "127",
  "closedDate": "2017-05-05"
}
```

### Example Response

```javascript
{
  "success": true,
  "id": 755
}
```

### `Update opportunity`

### Example Request

```javascript
{
  "id": 755,
  "venueId": "107",
  "name": "Updated Name"
}
```

### Example Response

```javascript
{
  "success": true,
  "id": 755
}
```

