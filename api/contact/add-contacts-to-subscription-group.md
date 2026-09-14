# Add Contacts To Subscription Group

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="contact?action=addContactsToSubscriptionGroup" method="post" summary="Add Contacts To Subscription Group" %}
{% swagger-description %}
Add contact details to subscription group
{% endswagger-description %}

{% swagger-parameter name="contacts" type="integer" in="path" %}
The contact identifiers to subscribe to the group. This is an array of contact identifiers
{% endswagger-parameter %}

{% swagger-parameter name="group" type="integer" in="path" %}
The subscription group identifier to add the contacts to
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
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
{% endswagger-response %}
{% endswagger %}

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

| Property  | Description                                  |
| --------- | -------------------------------------------- |
| contactId | The contact this result is for               |
| status    | If the contact was added to the group or not |
