# Add or Update Opportunity

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateOpportunity" path="" %}
{% api-method-summary %}
Add or Update Opportunity
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
The unique identifier of opportunity  
\(Leave empty if adding a new opportunity\)
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The unique venue if of the opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="qualityId" type="integer" required=false %}
The quality of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="companyId" type="integer" required=false %}
The unique company id of opportunity  
\(Required when lead belongs to a company and the id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="industryId" type="integer" required=false %}
The unique industry id of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="sourceId" type="integer" required=false %}
The unique source id of opportunity  
\(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="referralContactId" type="integer" required=false %}
The contact Id of referral for "Referral Program" source.
\(Required when the source is Referral Program and referralContact parameter is missing \)
{% endapi-method-parameter %}

{% api-method-parameter name="referralContact" type="object" required=false %}
The data array of contact. See [addOrUpdateContact](contact/add-or-update-contact.md#add-or-update-contact) API in contact namespace for parameters.
{% endapi-method-parameter %}

{% api-method-parameter name="referralCompanyId" type="integer" required=false %}
The company Id of referral for "Referral Program" source.
\(Required when the source is Referral Program and referralCompany parameter is missing \)
{% endapi-method-parameter %}

{% api-method-parameter name="referralCompany" type="object" required=false %}
The data array of company. See [addOrUpdateCompany](contact/add-or-update-company.md#add-or-update-company) API in contact namespace for parameters.
{% endapi-method-parameter %}

{% api-method-parameter name="confirmedQuoteId" type="integer" required=false %}
The unique confirmed quote id of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="confirmedQuoteStatus" type="integer" required=false %}
The status id of the confirmed quote
{% endapi-method-parameter %}

{% api-method-parameter name="cancelledQuoteId" type="integer" required=false %}
The unique cancelled quote id of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="lostToCompetition" type="integer" required=false %}
The ID of the lost reason
{% endapi-method-parameter %}

{% api-method-parameter name="closedDate" type="string" required=false %}
The close date of the opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="companyLeadContactId" type="integer" required=false %}
The unique contact ID of the company contact  
\(Required when lead belongs to company and id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="contactId" type="integer" required=false %}
The unique contact id of opportunity  
\(Required when opportunity belongs to contact and id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
The name for the opportunity  
\(Required when id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="ownerUserId" type="integer" required=false %}
The sales person id of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="typeId" type="integer" required=false %}
The type of opportunity  
\(Required when id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="stageId" type="integer" required=false %}
The stage of opportunity  
\(Required when id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="stageReasonId" type="integer" required=false %}
The unique stage reason id of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="channelId" type="string" required=false %}
The channel id of Opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
The description for the opportunity
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "success": true,
  "id": 755
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

### Add Opportunity

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

### Update Opportunity

```javascript
{
  "id": 755,
  "venueId": "107",
  "name": "Updated Name"
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the opportunity was added to the venue |
| id | The unique id of the opportunity |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24221 | The request is empty |
| Specific Code: 24222 | The opportunity does not exist |
| Specific Code: 24224 | The opportunity details are invalid |

This call takes values for a opportunity, and either

1. Updates the values for that opportunity \(after you have provided an id in the parameters\), or
2. Adds the opportunity to the system \(if the id parameter is missing\) 1. The result of this call will contain the status of the result \(either

   true or false\) and the opportunity identifier of the updated or newly

   created opportunity.

