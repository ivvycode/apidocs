# Get Registration

{% swagger baseUrl="[PlatformAddress]/api/1.0/event?action=getRegistration" method="post" summary="Get Registration" %}
{% swagger-description %}
Get Registration Details
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The registration identifier
{% endswagger-parameter %}

{% swagger-parameter name="eventId" type="integer" in="path" %}
The event identifier to which registration belongs
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Returns

| Property         | Description                                                 |
| ---------------- | ----------------------------------------------------------- |
| id               | The unique registration identifier                          |
| currentStatus    | The current status of the event                             |
| isExhibitor      | Whether or not event registration is exhibitor              |
| completedDate    | The registered date time of event registration              |
| firstName        | The first name of the event registration                    |
| lastName         | The last name of the event registration                     |
| phone            | The phone number of event registration                      |
| modifiedDate     | The date & time the registration was last modified          |
| mainContactId    | The id of the main contact for the event registration       |
| invoiceTotalCost | Total Cost of the invoices for the event registration       |
| invoiceTotalPaid | Total payments of the invoices for the event registration   |
| createdDate      | The date that the event registration was initially created. |

## Throws

| Code                 | Description             |
| -------------------- | ----------------------- |
| Specific Code: 24207 | Unable to find event    |
| Specific Code: 24208 | Invalid Registration Id |
| Specific Code: 24209 | Registration not found  |
