# Add or Update Lead

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="contact?action=addOrUpdateLead" method="post" summary="Add or Update Lead" %}
{% swagger-description %}
Add or update the details of a lead
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique identifier of a lead (Leave empty to add the lead to the system)
{% endswagger-parameter %}

{% swagger-parameter name="qualityId" type="integer" in="path" %}
The quality of the lead
{% endswagger-parameter %}

{% swagger-parameter name="industryId" type="integer" in="path" %}
The unique industry of the lead. (Required when lead belongs to contact and id parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="sourceId" type="integer" in="path" %}
The unique source id of the lead. (Required when the id parameter is missing. )
{% endswagger-parameter %}

{% swagger-parameter name="companyId" type="integer" in="path" %}
The unique company id of lead. (Required when lead belongs to company and id parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="company" type="object" in="path" %}
The data array of company. See addOrUpdateCompany API in contact namespace for parameters. See assigning a company/contact to the lead.
{% endswagger-parameter %}

{% swagger-parameter name="companyLeadContactId" type="integer" in="path" %}
The unique company id of lead (Required when lead belongs to company and id parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="contactId" type="integer" in="path" %}
The unique contact id of lead (Required when lead belongs to contact and id parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="contact" type="object" in="path" %}
The data array of contact. See addOrUpdateContact API in contact namespace for parameters. See assigning a company/contact to the lead.
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name for the lead (Required when the id parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="ownerUserId" type="integer" in="path" %}
The id of the sales person user assigned to the lead. The privileges of the user assigned to the api key may prevent this from being changed.
{% endswagger-parameter %}

{% swagger-parameter name="typeId" type="integer" in="path" %}
The type of lead (Required when id parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="stageId" type="integer" in="path" %}
The stage of lead (Required when id parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="stageReasonId" type="integer" in="path" %}
The unique stage reason id of opportunity
{% endswagger-parameter %}

{% swagger-parameter name="channelId" type="integer" in="path" %}
The channel Id of lead
{% endswagger-parameter %}

{% swagger-parameter name="description" type="string" in="path" %}
The description for the lead
{% endswagger-parameter %}

{% swagger-parameter name="customFields" type="array" in="path" %}
The custom field values of the lead. A custom field value might be required depending on how it has been configured in the account. See Custom Field
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Custom Field

A lead custom field is an object with the following details.

| Property   | Type    | Required | Description                                                                    |
| ---------- | ------- | -------- | ------------------------------------------------------------------------------ |
| fieldId    | integer | required | The unique id of the lead custom field                                         |
| fieldValue | mixed   | required | The value of the lead custom field. Depends on the type of custom field value. |

## Special Considerations

### Assigning a company/contact to the lead

The _contact type_ of a lead is either a _company_ **or** a _contact_. When _companyId_ **or** _company_ is present in the request then the _contact type_ of the lead is set to _company_, and the _contactId_ **or** _contact_ must be a contact that belongs to that company. Otherwise the _contact type_ of the lead is set to _contact_ and contactId can be any valid contact in the account.

If _contact_ and _company_ are present in request then it will link given contact to company.

## Returns

| Property | Description                                      |
| -------- | ------------------------------------------------ |
| success  | Whether or not the lead was added to the account |
| id       | The unique id of the lead                        |

## Throws

| Code                 | Description                  |
| -------------------- | ---------------------------- |
| Specific Code: 24215 | The request is empty         |
| Specific Code: 24216 | The lead does not exist      |
| Specific Code: 24218 | The lead details are invalid |

This call takes values for a lead, and either

1. Updates the values for that lead (after you have provided an id in the parameters), or
2. Adds the lead to the system (if the id parameter is missing)

The result of this call will contain the status of the result (either true or false) and the lead identifier of the updated or newly created lead.
