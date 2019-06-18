# Get Attendee List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/event?action=getAttendeeList" path="" %}
{% api-method-summary %}
Get Attendee List
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="perPage" type="integer" required=true %}
The number of attendees to get in a single api all
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=true %}
The starting result of the page. Note this is zero based \(i.e. sending start = 0 will start from first result.
{% endapi-method-parameter %}

{% api-method-parameter name="eventId" type="integer" required=true %}
The event identifier
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

## Additional [Filter](../getting-started/interpreting-the-response/filtering.md) Properties

No filters available

## Returns

A collection object with the following properties in the results

| Property | Description |
| :--- | :--- |
| id | The unique registration identifier |
| registrationStatus | The registration status of the event attendee |
| contactId | The contactId of event attendee |
| ticketTitle | The title of ticket |
| firstName | The first name of the event attendee |
| lastName | The last name of the event attendee |
| email | The email address of the event attendee |
| hasAttended | Whether attendee has attended event or not |
| sessionHasAttended | Whether attendee has attended session or not |
| isPublic | Whether event attndee is public or not |
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

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24210 | Unable to find event |

