# Get Attendee

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/event?action=getAttendee" path="" %}
{% api-method-summary %}
Get Attendee
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The attendee identifier
{% endapi-method-parameter %}

{% api-method-parameter name="eventId" type="integer" required=true %}
The event identifier to which attendee belongs
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

| Property | Description |
| :--- | :--- |
| id | The unique registration identifier |
| registrationStatus | The registration status of the event attendee |
| contactId | The contactId of event attendee |
| registrationId | The registration id of event attendee |
| ticketTitle | The title of ticket |
| firstName | The first name of the event attendee |
| lastName | The last name of the event attendee |
| email | The email address of the event attendee |
| hasAttended | Whether attendee has attended event or not |
| sessionHasAttended | Whether attendee has attended session or not |
| isPublic | Whether event attendee is public or not |
| barcode | The barcode text of event attendee |
| barcodeUrl | The barcode url of event attendee |
| ticketUrl | The ticket url of event attendee |
| attendedDatetime | The attended date time of event attendee |
| sessionAttendedTimestamp | The session attended date time of event attendee |
| cost | The cost of ticket of event attendee |
| customFields | The array of custom fields data of event attendee with below details |

## Custom field details

| Property | Description |
| :--- | :--- |
| name | The name of the custom field |
| value | The value of the custom field for attendee |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24211 | Unable to find event |
| Specific Code: 24212 | Invalid Attendee Id |
| Specific Code: 24213 | Attendee not found |

