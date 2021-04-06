# Get Account User List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/account?action=getUserList" path="" %}
{% api-method-summary %}
Get User List
{% endapi-method-summary %}

{% api-method-description %}
Get User List will respond with a list of users based on the filter parameters
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

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Additional [Filter](../getting-started/interpreting-the-response/filtering.md) Properties

| Property | Description | Type |
| :--- | :--- | :--- |
| venueId | Filter by specific Venue | integer |

## Returns

| Property | Description |
| :--- | :--- |
| id | The unique identifier for the user |
| salutation | The salutation of the user. |
| firstName | The first name of the user. |
| middleName | The middle name of the user. |
| lastName | The last name of the user. |
| email | The user’s email address |
| phone | The user’s mobile number |
| phoneMobile | The user’s phone number |
| currentStatus | The current status of the user. See [Current Status](get-user-list.md#user-current-status) |
| userType | The type of the user. See [User Types](get-user-list.md#user-types). |
| groupId | The id of the group to which the user belongs |
| lastLoginDate | The date & time the user was last logged in. |
| createdDate | The date & time the resource was created |
| modifiedDate | 'The date & time the resource was last modified |

## User Current Status

| \# | Description |
| :--- | :--- |
| 1 | Active |
| 2 | Inactive |

## User Types

| \# | Description |
| :--- | :--- |
| 1 | Normal |
| 2 | Abstract Reviewer |
| 3 | Event Client |
| 4 | API Third Party User |
| 5 | Meeting Booker |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the users. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

