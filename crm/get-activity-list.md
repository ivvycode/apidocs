# Get Activity List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="crm?action=getActivityList" method="post" summary="Get Activity List" %}
{% swagger-description %}
Get a list of activities.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the activity belongs
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
            "id": 29,
            "venueId": 1,
            "leadId": 400,
            "subType": 1,
            "name": "ashik testing",
            "description": "<p>this is description</p> ",
            "purposeName": null,
            "purposeType": null,
            "location": "Gold Coast",
            "contactId": null,
            "companyId": null,
            "companyContactId": null,
            "assignedUserId": 1,
            "assignedUserFullName": "first last",
            "assignedUserEmail": "first.last@domain.com",
            "startDatetime": "2019-04-02 22:00:00 UTC",
            "endDatetime": "2019-04-02 23:00:00 UTC",
            "createdDate": "2019-04-11 07:34:16 UTC",
            "modifiedDate": "2019-04-11 07:34:16 UTC"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the activities the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venue’s activity List`

```javascript
{
  "venueId": "1",
}
```

## subType:

One of the following values:

* 1 = Meeting
* 2 = Call
* 3 = Email
