# Add or Update Lead

### Description

Add or update lead detail.

### API URL

`[PlatformAddress]/api/1.0/contact?action=addOrUpdateLead`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| id | The unique identifier of lead\(Leave empty to add the lead to the system.\) | Required | integer |
| qualityId | The quality of lead | Required | integer |
| industryId | The unique industry id of lead | Required when lead belongs to contact and id parameter is missing | integer |
| sourceId | The unique source id of lead |  | integer |
|  |  | Required when the id parameter is missing |  |
| companyId | The unique company id of lead | Required when lead belongs to company and id parameter is missing | integer |
| companyLeadContactId | The unique company id of lead | Required when lead belongs to company and id parameter is missing | integer |
| contactId | The unique contact id of lead | Required when lead belongs to contact and id parameter is missing | integer |
| name | The name for the lead | Required when the id parameter is missing |  |
| ownerUserId | The sales person id of lead |  | integer |
| typeId | The type of lead |  | integer |
|  |  | Required when the id parameter is missing |  |
| stageId | The stage of lead |  | integer |
|  |  | Required when the id parameter is missing |  |
| channel | The channel of lead |  | integer |
| description | The description for the lead |  | integer |

### Returns

| Property | Description |
| --- | --- |
| success | Whether or not the lead was added to the account |
| id | The unique id of the lead |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24215 | The request is empty |
| Specific Code: 24216 | The lead does not exist |
| Specific Code: 24218 | The lead details are invalid |

This call takes values for a lead, and either

1. Updates the values for that lead \(after you have provided an id in the parameters\), or
2. Adds the lead to the system \(if the id parameter is missing\)

The result of this call will contain the status of the result \(either true or false\) and the lead identifier of the updated or newly created lead.

