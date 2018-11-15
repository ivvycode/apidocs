# Add or Update Contact

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/contact?action=addOrUpdateContact" path="" %}
{% api-method-summary %}
Add or Update Contact
{% endapi-method-summary %}

{% api-method-description %}
Add or update contact details
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="externalId" type="string" required=false %}
Reference to the ID of the contact in an external system.
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="integer" required=false %}
The contact's identifier. \(Leave empty to add new contact\)
{% endapi-method-parameter %}

{% api-method-parameter name="firstName" type="string" required=true %}
The contact's first name \(required when id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="LastName" type="string" required=true %}
The contact's last name \(required when id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
The contact's email address. Must be a valid email. \(required when id is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=false %}
The contacts phone number.
{% endapi-method-parameter %}

{% api-method-parameter name="groups" type="string" required=false %}
The array of subscription groups to set for the contact. Note: This list will override any groups currently set for the contact.
{% endapi-method-parameter %}

{% api-method-parameter name="customFields" type="string" required=false %}
The array of custom fields to set on the contact. Each field will be validated depending on the type of field that is set.
{% endapi-method-parameter %}

{% api-method-parameter name="companies" type="string" required=false %}
The array of companies to set on the contact. Each value will be validated depending on the type of field as well as it will verify that the given company exists or not.
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="enum" required=false %}
The contact's email subscription status.
{% endapi-method-parameter %}

{% api-method-parameter name="smsStatus" type="enum" required=false %}
The contact's sms subscription status. 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "id":33884
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request: Adding a contact

```javascript
{
  "firstName": "Bobby",
  "lastName": "Smith",
  "email": "bobbysmith@hotmail.com",
  "groups": [
    {
      "groupId": 10
    }
  ],
  "customFields": [
    {
      "fieldId": 33443,
      "value": "No"
    }
  ],
  "companies": [
    4,
    5
  ],
  "status": 2,
  "smsStatus": 2,
  "externalId" : "12345"
}
```

## Example Request: Updating a contact

`Note : the groups will be set to only group 10, destroying the existing value`

```javascript
{
  "id":33884,
  "firstName":"Bobby",
  "groups":[{"groupId":10}],
  "customFields":[{"fieldId":33443,"value":"No"}],
  "companies":[4,5],
  "status": 2,
  "smsStatus": 2,
}
```

This call takes values for a contact, and either

1. Updates the values for that contact \(after you have provided an id in the parameters\), or
2. Adds the contact to the system \(if the id parameter is missing\)

The result of this call will contain the status of the result \(either true or false\) and the contact identifier of the updated or newly created contact.

The properties of the contact currently supported are:

* firstName
* lastName
* email
* phone
* groups
  * This is an array of group objects with the ‘groupId’ key.
* customFields
  * This is an array of custom field objects with ‘fieldId’ and ‘value’ keys
* Companies
  * This is an array of companies Ids
* status
  * The current status of the email susbcription in contact. The value of this field will be [one of the following current status](add-or-update-contact.md#email-status)
* smsStatus
  * The current status of the sms susbcription in contact. The value of this field will be [one of the following current status](add-or-update-contact.md#sms-status)

## Returns

| Property | Description |
| :--- | :--- |
| success | If the contact was successfully added or updated |
| id | The unique identifier for the contact |
| message | Message of the failure \(if success was false\) |

### Email Status

The status is the record of whether the contact has opted in to email communication.

| **\#** | **Description** |
| :--- | :--- |
| 1 | Subscribed |
| 2 | Unsubscribed |
| 3 | Bounced |
| 4 | Registering |
| 5 | No Marketing |

### Sms status

The sms status is the record of whether the contact has opted in to sms communication.

| **\#** | **Description** |
| :--- | :--- |
| 1 | Subscribed |
| 2 | Unsubscribed |
| 3 | Failed |
| 4 | No Marketing |

