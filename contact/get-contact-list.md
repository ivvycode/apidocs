# Get Contact List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/contact?action=getContactList" path="" %}
{% api-method-summary %}
Get Contact List
{% endapi-method-summary %}

{% api-method-description %}
Get Contact List will respond with a list of contacts based on the filter parameters
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="perPage" type="integer" required=true %}
The number of events to get in a single api call
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=true %}
The starting result of the page. Note this is zero based \(i.e. sending start = 0 will start from the first result.\)
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

## Additional [Filter](../getting-started/interpreting-the-response/filtering.md) Properties

| Property | Description | Type |
| :--- | :--- | :--- |
| fromModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| toModifiedDate | Filter by Modified Date | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |

## Returns

| Property | Description |
| :--- | :--- |
| id | The unique identifier for the contact |
| firstName | The contact’s first name |
| lastName | The contact’s last name |
| email | The contact’s email address |
| phone | The contact’s phone number |
| customFields | The custom field information for the contact. This is an array of fields, each an object with the [keys](get-contact-list.md#keys). |
| groups | The subscription group information for the contact. |
| companies | This will an array company ids to which the contact belongs. |
| externalId | This will be external id of the contact |
| modifiedDate | The modified date of the contact |

## keys

| fieldId |
| :--- |
| displayName |
| value |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

