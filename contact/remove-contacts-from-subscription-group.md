# Remove Contacts From Subscription Group

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/contact?action=removeContactsFromSubscriptionGroup" path="" %}
{% api-method-summary %}
Remove Contacts From Subscription Groups
{% endapi-method-summary %}

{% api-method-description %}
Remove contact details from a subscription group
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="contacts" type="integer" required=true %}
The contact identifiers to unsubscribe from the group
{% endapi-method-parameter %}

{% api-method-parameter name="" type="integer" required=true %}
The subscription group identifier to remove the contacts from
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

## Returns

An array of objects with the following properties

| Property | Description |
| :--- | :--- |
| contactId | The contact this result is for |
| status | If the contact was removed from the group or not |

Removes a number of contacts from a subscription group. This call is very similar to the [addContactsToSubscriptionGroup](add-contacts-to-subscription-group.md) call. It takes the same parameters and returns the same result.

