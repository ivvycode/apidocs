# Get Attendee List

{% swagger baseUrl="[PlatformAddress]/api/1.0/event?action=getAttendeeList" method="post" summary="Get Attendee List" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of attendees to get in a single api all
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="path" %}
The starting result of the page. Note this is zero based (i.e. sending start = 0 will start from first result.
{% endswagger-parameter %}

{% swagger-parameter name="eventId" type="integer" in="path" %}
The event identifier
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Additional [Filter](../getting-started/interpreting-the-response/filtering.md) Properties

No filters available

## Returns

A collection object with the following properties in the results

| Property                 | Description                                                                                                                                                                                     |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                       | The unique registration identifier                                                                                                                                                              |
| registrationStatus       | The registration status of the event attendee                                                                                                                                                   |
| contactId                | The contactId of event attendee                                                                                                                                                                 |
| ticketTitle              | The title of ticket                                                                                                                                                                             |
| firstName                | The first name of the event attendee                                                                                                                                                            |
| lastName                 | The last name of the event attendee                                                                                                                                                             |
| email                    | The email address of the event attendee                                                                                                                                                         |
| hasAttended              | Whether attendee has attended event or not                                                                                                                                                      |
| sessionHasAttended       | Whether attendee has attended session or not                                                                                                                                                    |
| isPublic                 | Whether event attndee is public or not                                                                                                                                                          |
| barcode                  | The barcode text of event attendee                                                                                                                                                              |
| barcodeUrl               | The barcode url of event attendee                                                                                                                                                               |
| ticketUrl                | The ticket url of event attendee                                                                                                                                                                |
| attendedDatetime         | The attended date time of event attendee                                                                                                                                                        |
| sessionAttendedTimestamp | The session attended date time of event attendee                                                                                                                                                |
| cost                     | The cost of ticket of event attendee                                                                                                                                                            |
| customFields             | The array of custom fields data of event attendee with below details                                                                                                                            |
| createdDate              | The date & time the attendee was created                                                                                                                                                        |
| modifiedDate             | The date & time the attendee was last modified. Note: Updating the contact details of an Attendee changes the modifiedDate of the Contact. It does not change the modifiedDate of the Attendee. |

## Custom field details

| Property | Description                                |
| -------- | ------------------------------------------ |
| name     | The name of the custom field               |
| value    | The value of the custom field for attendee |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Throws

| Code                 | Description          |
| -------------------- | -------------------- |
| Specific Code: 24210 | Unable to find event |
