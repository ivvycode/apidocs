# Add or Update Opportunity

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateOpportunity" path="" %}
{% api-method-summary %}
Add or Update Opportunity
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the opportunity to add or update. See below for the data description.
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

## Opportunity

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique identifier of opportunity. A new opportunity will be created if this parameter is not present. |
| venueId | integer | required | The unique id of the venue to which the opportunity belongs. |
| name | string | optional | The name for the opportunity \(Required when id is missing\). |
| description | string | optional | The description for the opportunity. |
| companyId | integer | optional | The unique id of the company to assign to the opportunity. See [assigning a company/contact to the opportunity](add-or-update-opportunity.md#assigning-a-company-contact-to-the-opportunity). |
| company | object | optional | The data array of company. See addOrUpdateCompany API in contact namespace for parameters. |
| companyLeadContactId | integer | optional | The unique id of the company contact to assign to the opportunity See [assigning a company/contact to the opportunity](add-or-update-opportunity.md#assigning-a-company-contact-to-the-opportunity). |
| contactId | integer | optional | The unique id of the contact to assign to the opportunity See [assigning a company/contact to the opportunity](add-or-update-opportunity.md#assigning-a-company-contact-to-the-opportunity). |
| contact | object | optional | The data array of contact. See addOrUpdateContact API in contact namespace for parameters. |
| qualityId | integer | optional | The unique id of the quality. |
| industryId | integer | optional | The unique id of industry. |
| sourceId | integer | optional | The unique id of source \(Required when the ID parameter is missing\) |
| ownerUserId | integer | optional | The id of the sales person user assigned to the opportunity. The privileges of the user assigned to the api key may prevent this from being changed. |
| typeId | integer | optional | The unique id of type \(Required when id is missing\). |
| stageId | integer | optional | The unique id of stage. |
| stageReasonId | integer | optional | The unique stage reason id of opportunity. |
| channelId | integer | optional | The unique id of channel. |
| utmSource | string | optional | The source of the campaign. (only when adding) |
| utmMedium | string | optional | What medium the campaign used/uses. (only when adding)|
| utmCampaign | string | optional | The name of the campaign. (only when adding)|
| utmTerm | string | optional | The Term of the campaign. (only when adding)|
| utmContent | string | optional | Any content about the campaign. |
| referralContactId | integer | optional | The contact Id of referral for "Referral Program" source. \(Required when the source is Referral Program and referralContact parameter is missing\) |
| referralContact | object | optional | The data array of contact. See addOrUpdateContact API in contact namespace for parameters. |
| referralCompanyId | integer | optional | The company Id of referral for "Referral Program" source. \(Required when the source is Referral Program and referralCompany parameter is missing\) |
| referralCompany | object | optional | The data array of company. See addOrUpdateCompany API in contact namespace for parameters. |
| confirmedQuoteId | integer | optional | The unique if of confirmed quote to which the opportunity belongs. |
| confirmedQuoteStatus | integer | optional | The status of the confirmed quote to which the opportunity belongs. |
| cancelledQuoteId | integer | optional | The unique id of cancelled quote to which the opportunity belongs. |
| lostToCompetition | integer | optional | The unique id of lost reason. |
| closedDate | date | optional | The close date of the opportunity. |
| customFields | array | optional | The custom field values of the opportunity. A custom field value might be required depending on how it has been configured in the venue's account. See [Custom Field](add-or-update-opportunity.md#custom-field) |

## Custom Field

A opportunity custom field is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| fieldId | integer | required | The unique id of the opportunity custom field |
| fieldValue | mixed | required | The value of the opportunity custom field. Depends on the type of custom field value. |

## Special Considerations

### Assigning a company/contact to the opportunity

The _contact type_ of a opportunity is either a _company_ **or** a _contact_. When _companyId_ **or** _company_ is present in the request then the _contact type_ of the opportunity is set to _company_, and the _companyLeadContactId_ **or** _contact_ must be a contact that belongs to that company. Otherwise the _contact type_ of the opportunity is set to _contact_ and contactId can be any valid contact in the venue's account.

If _contact_ and _company_ are present in request then it will link given contact to company.

## Example Request

### Add Opportunity

```javascript
{
  "venueId": "107",
  "name": "Lead By API",
  "company" : {
        "businessName": "Business Name",
      "updateIfExists": true
  },
  "contact" : {
      "firstName" : "First",
      "lastName" : "Last",
      "email" : "email8@email.com",
      "updateIfExists" : true
  },
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
2. Adds the opportunity to the system \(if the id parameter is missing\)

The result of this call will contain the status of the result \(either true or false\) and the opportunity identifier of the updated or newly

