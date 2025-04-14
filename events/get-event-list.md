# Get Event List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="event?action=getEventList" method="get" summary="getEventList" %}
{% swagger-description %}
Get List of Events
{% endswagger-description %}

{% swagger-parameter name="perPage" type="integer" in="body" %}
The number of events to get in a single api call
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="body" %}
The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result)
{% endswagger-parameter %}

{% swagger-parameter name="includeVenueDetails" type="boolean" in="body" %}
If the response should include venue details
{% endswagger-parameter %}

{% swagger-parameter name="includeTicketDetails" type="boolean" in="body" %}
If the response should include ticket details
{% endswagger-parameter %}

{% swagger-parameter name="includeInformationDetails" type="boolean" in="body" %}
If the response should include the event information
{% endswagger-parameter %}

{% swagger-parameter name="includeHomepageContent" type="boolean" in="body" %}
If the response should include the homepage content of the website
{% endswagger-parameter %}

{% swagger-parameter name="orderBy" type="string" in="body" %}
Sort Results: Support Parameter 'startDate'
{% endswagger-parameter %}

{% swagger-parameter name="orderDir" type="string" in="body" %}
Sort Direction: Support Parameter 'asc' or 'desc'
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Additional [Filter ](../getting-started/interpreting-the-response/filtering.md)Properties

| Property   | Description                                    | Type                                                                  |
| ---------- | ---------------------------------------------- | --------------------------------------------------------------------- |
| afterDate  | Filter by start date                           | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| beforeDate | Filter by end date                             | [iVvy Timestamp Format](../development-reference/timestamp-format.md) |
| status     | Filter by status Array of the following values | Must be an array                                                      |

## Returns

A collection object with the following properties in the results.

| Property                      | Description                                                                                                                                                                                                 |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                            | The unique event identifier                                                                                                                                                                                 |
| code                          | The code for the event                                                                                                                                                                                      |
| eventType                     | [The type of event.](get-event-list.md#event-types)                                                                                                                                                         |
| title                         | The title of the event                                                                                                                                                                                      |
| domainName                    | The domain name of the event                                                                                                                                                                                |
| startDateTime                 | The start of the event, at UTC                                                                                                                                                                              |
| endDateTime                   | The end of the event, at UTC                                                                                                                                                                                |
| numRegistered                 | The number of registrations                                                                                                                                                                                 |
| currentStatus                 | [The current status of the event](get-event-list.md#current-status-of-event)                                                                                                                                |
| contactEmail                  | The contact email address on the event                                                                                                                                                                      |
| websiteUrl                    | The URL for the event website                                                                                                                                                                               |
| websiteTemplateBannerImageUrl | Banner that is displayed on the website                                                                                                                                                                     |
| venue                         | [Details of the venue of the event (if the includeVenueDetails flag is set on the request)](get-event-list.md#venue-details)                                                                                |
| tickets                       | [The tickets of an event (if the includeTicketDetails flag is set on the request)](get-event-list.md#event-ticket-details)                                                                                  |
| information                   | [Event website information (if the includeInformationDetails flag is set on the request) This is an array of objects with the information properties](get-event-list.md#event-website-information-details). |
| homepageContent               | Content of the website home page (if the includeHomepageContent flag is set on the request). Note this is the contents of the HTML that is entered in as the home page content of the event.                |
| eventTags                     | [The tags of the event.](get-event-list.md#event-tags)                                                                                                                                                      |
| modifiedDate                  | timestamp                                                                                                                                                                                                   |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

### Event types

| Type | Description          |
| ---- | -------------------- |
| 0    | Other                |
| 1    | Party                |
| 2    | Festival             |
| 3    | Golf Day             |
| 4    | Wedding              |
| 5    | Meeting              |
| 6    | Seminar              |
| 7    | Conference           |
| 8    | Exhibition           |
| 9    | Roadshow             |
| 10   | Simple               |
| 11   | Party (21st / 18th)  |
| 12   | Record Event Details |

The result from this call will be a collection of all the events the user has access to. This call also accepts the pagination and filter properties.

### Current status of event

| Code | Description |
| ---- | ----------- |
| 0    | Draft       |
| 1    | Closed      |
| 3    | Launched    |

### Venue details

| Property    | Description                       |
| ----------- | --------------------------------- |
| name        | The venue name                    |
| description | The description of the venue      |
| address     | The address of the venue          |
| imageUrl    | The URL to the image of the venue |

### Event ticket details

| Property           | Description                                                                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                 | The unique identifier for the ticket                                                                                                                    |
| title              | Title of the ticket                                                                                                                                     |
| capacity           | Capacity of the ticket                                                                                                                                  |
| description        | Description of the ticket                                                                                                                               |
| amount             | Amount of the ticket                                                                                                                                    |
| isTaxFree          | Amount of the ticket is tax free                                                                                                                        |
| subscriptionGroups | [Subscription groups assigned to the ticket This an array of objects with subscription group properties](get-event-list.md#subscription-group-details). |

### Subscription group details

| Property  | Description                         |
| --------- | ----------------------------------- |
| id        | The subscription group identifier   |
| groupName | The name for the group              |
| tagColour | The designated colour for the group |

### Event website information details

| Property    | Description                                |
| ----------- | ------------------------------------------ |
| description | Description of the information             |
| information | Content of the information                 |
| fileUrl     | Attached file url of event information     |
| sortOrder   | The order in which to sort the information |

### Event tags

| Property | Description                             |
| -------- | --------------------------------------- |
| id       | The unique identifier for the event tag |
| name     | The name of the event tag               |
