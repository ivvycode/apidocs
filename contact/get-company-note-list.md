# Get Company Note List

{% swagger baseUrl="[PlatformAddress]/api/1.0/contact?action=getCompanyNoteList" method="post" summary="Get Company Note List" %}
{% swagger-description %}
Fetches a list of notes for a specific company.
{% endswagger-description %}

{% swagger-parameter name="companyId" type="integer" in="path" %}
The unique identifier of the company to which the company notes belong
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of company notes to fetch
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
            "accountId": 0,
            "companyId": 4,
            "noteText": "<p>Company Note 1</p>\n",
            "createdByUserId": 1,
            "createdDate": "2022-06-12 06:06:03 UTC",
            "modifiedDate": "2022-07-13 01:32:10"
        },
        {
            "id": 4,
            "accountId": 0,
            "companyId": 4,
            "noteText": "<p>Company Note 2</p>\n",
            "createdByUserId": 1,
            "createdDate": "2022-07-13 01:27:27 UTC",
            "modifiedDate": "2022-07-13 01:27:27"
        },
        {
            "id": 5,
            "accountId": 0,
            "companyId": 4,
            "noteText": "<p>Company Note 3</p>\n",
            "createdByUserId": 1,
            "createdDate": "2022-07-13 01:29:41 UTC",
            "modifiedDate": "2022-07-13 01:29:41"
        },
    ]
}

```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md)  of company note to which the user has access. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Fetches a list of Notes for a specific Company`

```javascript
{
    "companyId" : 4,
    "perPage" : 50
}
```
## Company Note

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the company note |
| companyId | required  | integer | The id of the company to which the company note belongs |
| noteText | required  | string | The company note |
| createdByUserId | optional  | integer | The details of person who created the company note |
| createdDate | optional  | string | The date & time the company note was created |
| modifiedDate | optional  | string | The date & time the company note was last modified |