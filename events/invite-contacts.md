# Invite Contacts

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/event?action=inviteContacts" path="" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
Invite contact\(s\) to event. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="event" type="integer" required=true %}
The event identifier to invite the contact to
{% endapi-method-parameter %}

{% api-method-parameter name="contacts" type="integer" required=true %}
An array of contact identifiers to invite to the event 
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "results":[
        {
            "contact":1,
            "status":true,
            "inviteLinkYes":"http://....",
            "inviteLinkNo":"http://...."
        },
        {   "contact":2,
            "status":false},
        {
            "contact":3,
            "status":true
            "inviteLinkYes":"http://....",
            "inviteLinkNo":"http://...."
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Example: Invite contacts with identifiers 1, 2 and 3 to event with the identifier 4`

```javascript
{
  "event":4,
  "contacts":[1,2,3]
}
```

## Returns

| Property | Description |
| --- | --- |
| results | An array of objects with the following properties |
| contact | The contact identifier |
| status | The status of the request |
| inviteLinkYes | Invitation link for the YES responses |
| inviteLinkNo | Invitation link fo the NO responses |

To invite a contact to the event, pass through the event identifier and an array of contact identifiers through to this call. The result will be a an array indicating if each of the contacts invitation was successful or not, and if so the links for responding to the invitations for both yes and no.

