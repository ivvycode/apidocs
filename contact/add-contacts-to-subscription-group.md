# Add Contacts To Subscription Group

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/contact?action=addContactsToSubscriptionGroup" path="" %}
{% api-method-summary %}
Add Contacts To Subscription Group
{% endapi-method-summary %}

{% api-method-description %}
Add contact details to subscription group
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="contacts" type="integer" required=true %}
The contact identifiers to subscribe to the group. This is an array of contact identifiers
{% endapi-method-parameter %}

{% api-method-parameter name="group" type="integer" required=true %}
The subscription group identifier to add the contacts to
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
[
  {
    "contactId": 4,
    "status": true
  },
  {
    "contactId": 6,
    "status": true
  },
  {
    "contactId": 55,
    "status": true
  },
  {
    "contactId": 33,
    "status": false
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

```javascript
{
  "contacts": [
    4,
    6,
    55,
    33
  ],
  "group": 2481
}
```

## Returns

An array of objects with the following properties

| Property | Description |
| :--- | :--- |
| contactId | The contact this result is for |
| status | If the contact was added to the group or not |

