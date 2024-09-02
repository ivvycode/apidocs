# Get Task List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="crm?action=getTaskList" method="post" summary="Get Task List" %}
{% swagger-description %}
Get a list of tasks.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the task belongs
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
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
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the tasks the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venue’s task List`

```javascript
{
  "venueId": "1",
}
```

## status:

One of the following values:

* 0 = Not Started
* 1 = In Progress
* 2 = On Hold
* 3 = Cancelled
* 4 = Completed
