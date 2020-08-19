# Get Opportunity Allocation Users

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=getOpportunityAllocationUsers" path="" %}
{% api-method-summary %}
Get Opportunity Allocation Users
{% endapi-method-summary %}

{% api-method-description %}
Get a list of ids and emails for users eligible for assigning to a Marketplace Lead based on the configured 
Opportunity Allocation Rules. Results also include Notify Emails that are configured on the Opportunity Allocation Rule.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The venue id for the opportunity.
{% endapi-method-parameter %}

{% api-method-parameter name="estimatedValue" type="integer" required=false %}
The estimated value of the opportunity to filter Opportunity Allocation Rules by.
{% endapi-method-parameter %}

{% api-method-parameter name="eventType" type="integer" required=false %}
The eventType of the opportunity to filter Opportunity Allocation Rules by.
{% endapi-method-parameter %}

{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 6,
        "start": null,
        "perPage": 100,
        "count": 6
    },
    "results": [
        {
            "id": 0,
            "email": "one@notifyEmail.com"
        },
        {
            "id": 0,
            "email": "two@notifyEmail.com"
        },
        {
            "id": 1,
            "email": "venue@admin.com"
        },
        {
            "id": 113,
            "email": "another@admin.com"
        },
        {
            "id": 3193,
            "email": "venue@admin.com"
        },
        {
            "id": 3195,
            "email": "first@last.com"
        },
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all emails eligible for assigning to the opportunity, based on the Opportunity Allocation Rules that are configured for the opportunity's Venue. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venues' opportunity allocation user emails.`

```javascript
{
    "perPage": 100,
    "start": 0,
    "filter": {
        "eventType": 2,
        "estimatedValue": 50
    }
}
```
## Returns

An array of objects with the following properties

| Property | Description |
| :--- | :--- |
| id | The id of the user. Will be `0` for Notify Emails. |
| email | The email address for the eligible user, or Notify Email configured for the Opportunity Allocation Rule. |

### Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24308 | EventType not found
