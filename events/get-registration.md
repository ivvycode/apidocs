# Get Registration

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/event?action=getRegistration" path="" %}
{% api-method-summary %}
Get Registration
{% endapi-method-summary %}

{% api-method-description %}
Get Registration Details
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The registration identifier
{% endapi-method-parameter %}

{% api-method-parameter name="eventId" type="integer" required=true %}
The event identifier to which registration belongs
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Returns

| Property | Description |
| --- | --- |
| id | The unique registration identifier |
| currentStatus | The current status of the event |
| isExhibitor | Whether or not event registration is exhibitor |
| completedDate | The registered date time of event registration |
| firstName | The first name of the event registration |
| lastName | The last name of the event registration |
| phone | The phone number of event registration |
| modifiedDate | The date & time the registration was last modified |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24207 | Unable to find event |
| Specific Code: 24208 | Invalid Registration Id |
| Specific Code: 24209 | Registration not found |

