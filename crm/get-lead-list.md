# Get Lead List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="crm?action=getLeadList" method="post" summary="Get Lead List" %}
{% swagger-description %}
Get a list of lead.
{% endswagger-description %}

{% swagger-parameter name="" type="string" in="path" %}

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
            "stageReasonId": 245,
            "stageReasonName": "Price under budget",
            "adminStatusChangedDate": "2019-04-12 11:11:00 UTC",
            "typeId": 3,
            "type": "Reseller",
            "subtypeId: 1,
            "sourceId": 13,
            "sourceName": "Newspaper",
            "channelId": 8,
            "channelName": "PCO",
            "leadBccEmail": "lead-2-763-facdb9@ivvy.blueweb",
            "closedDate": "2019-04-19 09:00:00 UTC",
            "lostToCompetition": "More capacity available",
            "createdDate": "2019-04-12 09:00:35 UTC",
            "modifiedDate": "2019-04-12 11:11:00 UTC"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the leads the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.
