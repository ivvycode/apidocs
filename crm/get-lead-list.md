# Get Lead List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=getLeadList" path="" %}
{% api-method-summary %}
Get Lead List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of lead.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

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
        "id": 763,
            "name": "Lead Name",
            "description": "This is test description",
        "ownerUser": {
                "id": 549,
                "firstName": "First",
                "lastName": "Last",
                "email": "first@last.com",
                "phone": ""
            },
        "contact": {
                "id": 580,
                "firstName": "First",
                "lastName": "last",
                "email": "filrst.last@email.com",
                "phone": 614535435
            },
        "company": {
                "id": 214,
                "businessName": "Company BusinessName",
                "businessNumber": "BUS123",
                "phone": null,
                "email": company@owner.com
            },
            "currentBookingId": 5,
            "qualityId": 2,
            "quality": "B-Grade",
            "stageId": 47,
            "stageName": "Interested",
            "typeId": 3,
            "type": "Reseller",
            "sourceId": 13,
            "sourceName": "Newspaper",
            "channelId": 8,
            "channelName": "PCO",
            "leadEmailAddress": "lead-2-763-facdb9@ivvy.blueweb",
            "createdDate": "2019-04-12 09:00:35 UTC",
            "modifiedDate": "2019-04-12 09:00:35 UTC"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the leads the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

