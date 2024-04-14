# Get Opportunity List

{% swagger baseUrl="[PlatformAddress]/api/1.0/crm?action=getOpportunityList" method="post" summary="Get Opportunity List" %}
{% swagger-description %}
Get a list of opportunity.
{% endswagger-description %}

{% swagger-parameter name="venueIds" type="integer" in="path" %}
The array of venue ids to which the opportunity belongs
{% endswagger-parameter %}

{% swagger-parameter name="orderBy" type="string" in="body" %}
Sort Results: Support Parameter 'id', 'modifiedDate'
{% endswagger-parameter %}

{% swagger-parameter name="orderDir" type="string" in="body" %}
Sort Direction: Support Parameter 'asc' or 'desc'
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
            "venueId": 1,
            "name": "Opprotunity Name",
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

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the opportunities the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venues' opportunity List`

```javascript
{
  "venueId": [1,2],
}
```
