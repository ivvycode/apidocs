# Get Task List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=getTaskList" path="" %}
{% api-method-summary %}
Get Task List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of tasks.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=false %}
The unique id of the venue to which the task belongs
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
        "totalResults": 1,
        "start": 0,
        "perPage": 100,
        "count": 1
    },
    "results": [
        {
            "id": 1,
            "venueId": 76,
            "leadId": null,
            "name": "test name",
            "description": "<p>this is description</p> ",
            "contactId": null,
            "companyId": null,
            "companyContactId": null,
            "assignedUserId": 1,
            "userFullName": "first last",
            "userEmail": "first@domain.com",
            "priority": "low",
            "startDatetime": "2018-03-01 09:00:00 UTC",
            "endDatetime": "2018-03-27 09:00:00 UTC",
            "progress": 0,
            "createdDate": "2018-03-01 10:13:17 UTC",
            "modifiedDate": "2018-03-26 11:17:05 UTC"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the tasks the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venue’s task List`

```javascript
{
  "venueId": "1",
}
```

