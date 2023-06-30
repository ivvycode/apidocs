# Get Contact List

{% swagger baseUrl="[PlatformAddress]/api/1.0/contact?action=getContactList" method="post" summary="Get Contact List" %}
{% swagger-description %}
Get Contact List will respond with a list of contacts based on the filter parameters
{% endswagger-description %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of events to get in a single api call
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="path" %}
The starting result of the page. Note this is zero based (i.e. sending start = 0 will start from the first result.)
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Additional [Filter](../getting-started/interpreting-the-response/filtering.md) Properties

| Property         | Description                    | Type                                                                  |
| ---------------- | ------------------------------ | --------------------------------------------------------------------- |
| fromModifiedDate | Filter by Modified Date        | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| toModifiedDate   | Filter by Modified Date        | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| externalId       | Filter by external unique id   | Unique external Id in string                                          |
| venueId          | Filter by specific Venue       | integer                                                               |
| venueGroupId     | Filter by specific Venue Group | integer                                                               |
| companyId        | Filter by specific Company Id  | integer                                                               |

## Returns

| Property      | Description                                                                                                                         |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| id            | The unique identifier for the contact                                                                                               |
| firstName     | The contact’s first name                                                                                                            |
| lastName      | The contact’s last name                                                                                                             |
| email         | The contact’s email address                                                                                                         |
| phone         | The contact’s phone number                                                                                                          |
| customFields  | The custom field information for the contact. This is an array of fields, each an object with the [keys](get-contact-list.md#keys). |
| groups        | The subscription group information for the contact.                                                                                 |
| companies     | This will an array company ids to which the contact belongs.                                                                        |
| companiesData | This will an array company containing id and businessName for each company to which the contact belongs.                            |
| externalId    | This will be external id of the contact                                                                                             |
| modifiedDate  | The modified date of the contact                                                                                                    |

## keys

| fieldId     |
| ----------- |
| displayName |
| value       |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.
