# Convert Lead To Opportunity

### Description

Convert lead to opportunity.

### API URL

`[PlatformAddress]/api/1.0/venue?action=convertLeadToOpportunity`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| leadId | The unique identifier of lead | Required | integer |
| venueId | The unique venue id of opportunity | Required | integer |
| stageId | The stage of opportunity | Required | integer |

### Returns

| Property | Description |
| --- | --- |
| success | Whether or not the lead was converted to opportunity or not |

### Throws

| Code | Description |
| --- | --- |
| Specific Code: 24227 | The request is empty |
| Specific Code: 24228 | The lead does not exist |

