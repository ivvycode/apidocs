# Get Subscription Group List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="contact?action=getSubscriptionGroupList" %}
{% api-method-summary %}
Get Subscription Group List
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

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

Subscription Groups are a feature that enables customers to segment their contacts into groups. These groups can then used for a range of purposes, including email and sms marketing, restricting access to event ticket types and content pages plus more.

## Returns

An array with the following properties

| Property | Description |
| :--- | :--- |
| id | The subscription group identifier |
| groupName | The name for the group |
| memberCount | The number of contacts in the group |
| tagColour | The designated colour for the group |

Returns an array of subscription groups available on the account.

