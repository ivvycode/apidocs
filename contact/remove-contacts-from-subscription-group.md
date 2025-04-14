# Remove Contacts From Subscription Group

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="contact?action=removeContactsFromSubscriptionGroup" method="post" summary="Remove Contacts From Subscription Groups" %}
{% swagger-description %}
Remove contact details from a subscription group
{% endswagger-description %}

{% swagger-parameter name="contacts" type="integer" in="path" %}
The contact identifiers to unsubscribe from the group
{% endswagger-parameter %}

{% swagger-parameter name="" type="integer" in="path" %}
The subscription group identifier to remove the contacts from
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Returns

An array of objects with the following properties

| Property  | Description                                      |
| --------- | ------------------------------------------------ |
| contactId | The contact this result is for                   |
| status    | If the contact was removed from the group or not |

Removes a number of contacts from a subscription group. This call is very similar to the [addContactsToSubscriptionGroup](add-contacts-to-subscription-group.md) call. It takes the same parameters and returns the same result.
