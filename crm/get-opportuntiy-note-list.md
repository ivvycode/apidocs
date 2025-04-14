# Get Opportunity Note List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="crm?action=getOpportunityNoteList" method="post" summary="Get Opportunity Note List" %}
{% swagger-description %}
Fetches a list of notes for a specific opportunity.
{% endswagger-description %}

{% swagger-parameter name="leadId" type="integer" in="path" %}
The unique identifier of the opportunity to which the opportunity notes belong
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique identifier of the venue to which the opportunity notes belong
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of opportunity notes to fetch
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="path" %}
The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.)
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 10,
        "start": 0,
        "perPage": 50,
        "count": 3
    },
    "results": [
        {
            "id": 2,
            "leadId": 4,
            "note": "<p>Opportunity Note 1</p>\n",
            "createdByUserId": 1,
            "createdDate": "2022-06-12 06:06:03 UTC",
            "modifiedDate": "2022-07-13 01:32:10"
        },
        {
            "id": 4,
            "leadId": 4,
            "note": "Opportunity Note 2",
            "createdByUserId": 1,
            "createdDate": "2022-07-13 01:27:27 UTC",
            "modifiedDate": "2022-07-13 01:27:27"
        },
        {
            "id": 5,
            "leadId": 4,
            "note": "Opportunity Note 3",
            "createdByUserId": 1,
            "createdDate": "2022-07-13 01:29:41 UTC",
            "modifiedDate": "2022-07-13 01:29:41"
        },
    ]
}

```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md)  of opportunity note to which the user has access. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Fetches a list of Notes for a specific Opportunity`

```javascript
{
    "venueId": 1
    "leadId" : 4,
    "perPage" : 50
}
```
## Opportunity Note

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the opportunity note |
| leadId | integer  | The opportunity to which the opportunity note belongs |
| note | string  | The opportunity note |
| createdByUserId | integer  | The details of person who created the opportunity note |
| createdDate | timestamp | The date & time the opportunity note was created |
| modifiedDate | timestamp | The date & time the opportunity note was last modified |