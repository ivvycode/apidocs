# Get Registration List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/event?action=getRegistrationList" path="" %}
{% api-method-summary %}
Get Registration List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of registrations
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="perPage" type="integer" required=true %}
The number of registrations to get in a single api call. Must be an integer greater than 0 and maximum 100
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=true %}
The starting result of the page. Note this is zero based \(i.e. sending start = 0 will start from first result\). Must be 0 or greater
{% endapi-method-parameter %}

{% api-method-parameter name="eventId" type="integer" required=true %}
The event identifier.
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

## Additional [Filter ](../getting-started/interpreting-the-response/filtering.md)Properties

| Property | Description | Type |
| :--- | :--- | :--- |
| modifiedDate | Filter by modified date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |

## Returns

A collection object with the following properties in the results

| Property | Description |
| :--- | :--- |
| id | The unique registration identifier |
| eventName | The name of event that event registration belongs |
| currentStatus | The current status of the event |
| isExhibitor | Whether or not event registration is exhibitor |
| completedDate | The registered date time of event registration |
| mainContactId | The main contact id of event registration |
| firstName | The first name of the event registration |
| lastName | The last name of the event registration |
| phone | The phone number of event registration |
| invoiceTotalCost | The total cost of event registration |
| invoiceTotalPaid | The total amount paid of event registration |
| createdDate | The date & time the registration was created |
| modifiedDate | The date & time the registration was last modified |

The result from this call will be a collection of all the events the user has access to. This call also accepts the pagination and filter properties.

The result from this call will be a [collection](./#collections) of all the events the user has access to. This call also accepts the [pagination](./#pagination) and [filter](./#filtering) properties.

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24206 | Unable to find event |

