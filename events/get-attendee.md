# Get Attendee

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="event?action=getAttendee" method="post" summary="Get Attendee" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The attendee identifier
{% endswagger-parameter %}

{% swagger-parameter name="eventId" type="integer" in="path" %}
The event identifier to which attendee belongs
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Returns

| Property                 | Description                                                          |
| ------------------------ | -------------------------------------------------------------------- |
| id                       | The unique registration identifier                                   |
| registrationStatus       | The registration status of the event attendee                        |
| contactId                | The contactId of event attendee                                      |
| registrationId           | The registration id of event attendee                                |
| ticketTitle              | The title of ticket                                                  |
| firstName                | The first name of the event attendee                                 |
| lastName                 | The last name of the event attendee                                  |
| email                    | The email address of the event attendee                              |
| hasAttended              | Whether attendee has attended event or not                           |
| sessionHasAttended       | Whether attendee has attended session or not                         |
| isPublic                 | Whether event attendee is public or not                              |
| barcode                  | The barcode text of event attendee                                   |
| barcodeUrl               | The barcode url of event attendee                                    |
| ticketUrl                | The ticket url of event attendee                                     |
| attendedDatetime         | The attended date time of event attendee                             |
| sessionAttendedTimestamp | The session attended date time of event attendee                     |
| cost                     | The cost of ticket of event attendee                                 |
| customFields             | The array of custom fields data of event attendee with below details |

## Custom field details

| Property | Description                                |
| -------- | ------------------------------------------ |
| name     | The name of the custom field               |
| value    | The value of the custom field for attendee |

## Throws

| Code                 | Description          |
| -------------------- | -------------------- |
| Specific Code: 24211 | Unable to find event |
| Specific Code: 24212 | Invalid Attendee Id  |
| Specific Code: 24213 | Attendee not found   |
