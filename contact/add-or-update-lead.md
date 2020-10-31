# Add or Update Lead

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/contact?action=addOrUpdateLead" path="" %}
{% api-method-summary %}
Add or Update Lead
{% endapi-method-summary %}

{% api-method-description %}
Add or update the details of a lead
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The unique identifier of a lead \(Leave empty to add the lead to the system\)
{% endapi-method-parameter %}

{% api-method-parameter name="qualityId" type="integer" required=true %}
The quality of the lead
{% endapi-method-parameter %}

{% api-method-parameter name="industryId" type="integer" required=false %}
The unique industry of the lead. \(Required when lead belongs to contact and id parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="sourceId" type="integer" required=false %}
The unique source id of the lead. \(Required when the id parameter is missing. \)
{% endapi-method-parameter %}

{% api-method-parameter name="companyId" type="integer" required=false %}
The unique company id of lead. \(Required when lead belongs to company and id parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="company" type="object" required=false %}
The data array of company. See addOrUpdateCompany API in contact namespace for parameters. See assigning a company/contact to the lead.
{% endapi-method-parameter %}

{% api-method-parameter name="companyLeadContactId" type="integer" required=false %}
The unique company id of lead \(Required when lead belongs to company and id parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="contactId" type="integer" required=false %}
The unique contact id of lead \(Required when lead belongs to contact and id parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="contact" type="object" required=false %}
The data array of contact. See addOrUpdateContact API in contact namespace for parameters. See assigning a company/contact to the lead.
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
The name for the lead \(Required when the id parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="ownerUserId" type="integer" required=false %}
The sales person id of lead
{% endapi-method-parameter %}

{% api-method-parameter name="typeId" type="integer" required=false %}
The type of lead \(Required when id parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="stageId" type="integer" required=false %}
The stage of lead \(Required when id parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="stageReasonId" type="integer" required=false %}
The unique stage reason id of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="channelId" type="integer" required=false %}
The channel Id of lead
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
The description for the lead
{% endapi-method-parameter %}

{% api-method-parameter name="customFields" type="array" required=false %}
The custom field values of the lead. A custom field value might be required depending on how it has been configured in the account. See Custom Field
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Custom Field

A lead custom field is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| fieldId | integer | required | The unique id of the lead custom field |
| fieldValue | mixed | required | The value of the lead custom field. Depends on the type of custom field value. |

## Special Considerations

### Assigning a company/contact to the lead

The _contact type_ of a lead is either a _company_ **or** a _contact_. When _companyId_ **or** _company_ is present in the request then the _contact type_ of the lead is set to _company_, and the _contactId_ **or** _contact_ must be a contact that belongs to that company. Otherwise the _contact type_ of the lead is set to _contact_ and contactId can be any valid contact in the account.

If _contact_ and _company_ are present in request then it will link given contact to company.

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the lead was added to the account |
| id | The unique id of the lead |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24215 | The request is empty |
| Specific Code: 24216 | The lead does not exist |
| Specific Code: 24218 | The lead details are invalid |

This call takes values for a lead, and either

1. Updates the values for that lead \(after you have provided an id in the parameters\), or
2. Adds the lead to the system \(if the id parameter is missing\)

The result of this call will contain the status of the result \(either true or false\) and the lead identifier of the updated or newly created lead.

