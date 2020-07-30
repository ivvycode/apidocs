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

{% api-method-parameter name="company" type="object" required=false %}
The data array of company. See addOrUpdateCompany API in contact namespace for parameters. See [assigning a company/contact to the opportunity](add-or-update-opportunity.md#assigning-a-company-contact-to-the-opportunity).
{% endapi-method-parameter %}

{% api-method-parameter name="industryId" type="integer" required=false %}
The unique industry id of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="sourceId" type="integer" required=false %}
The unique source id of opportunity
\(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="referralContactId" type="integer" required=false %}
The contact Id of referral for "Referral Program" source. \(Required when the source is Referral Program and referralContact parameter is missing \)
{% endapi-method-parameter %}

{% api-method-parameter name="referralContact" type="object" required=false %}
The data array of contact. See addOrUpdateContact API in contact namespace for parameters.
{% endapi-method-parameter %}

{% api-method-parameter name="referralCompanyId" type="integer" required=false %}
The company Id of referral for "Referral Program" source. \(Required when the source is Referral Program and referralCompany parameter is missing \)
{% endapi-method-parameter %}

{% api-method-parameter name="referralCompany" type="object" required=false %}
The data array of company. See addOrUpdateCompany API in contact namespace for parameters.
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

{% api-method-parameter name="contact" type="object" required=false %}
The data array of contact. See addOrUpdateContact API in contact namespace for parameters. See [assigning a company/contact to the opportunity](add-or-update-opportunity.md#assigning-a-company-contact-to-the-opportunity).
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

{% api-method-parameter name="customFields" type="array" required=false %}
The custom field values of the opportunity. A custom field value might be required depending on how it has been configured in the venue's account. See [Custom Field](add-or-update-opportunity.md#custom-field)
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

## Custom Field

A opportunity custom field is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| fieldId | integer | required | The unique id of the opportunity custom field |
| fieldValue | mixed | required | The value of the opportunity custom field. Depends on the type of custom field value. |

## Special Considerations

### Assigning a company/contact to the opportunity

The _contact type_ of a opportunity is either a _company_ **or** a _contact_. When _companyId_ **or** _company_ is present in the request then the _contact type_ of the opportunity is set to _company_, and the _contactId_ **or** _contact_ must be a contact that belongs to that company. Otherwise the _contact type_ of the opportunity is set to _contact_ and contactId can be any valid contact in the venue's account.

If _contact_ and _company_ are present in request then it will link given contact to company.

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
  "closedDate": "2017-05-05",
  "referralCompany": {
        "businessName": "Business",
        "primaryContact": {
            "firstName": "Test",
            "lastName": "Test",
            "email": "Test@gmail.com"
        }
    },
    "referralContact": {
        "firstName": "Test",
        "lastName": "Test",
        "email": "Test@gmail.com"
    }
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

