# Get Company Note List

## Get Company Note List

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/contact?action=getCompanyNoteList`

Fetches a list of notes for a specific company.

#### Path Parameters

| Name      | Type    | Description                                                                                                       |
| --------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| companyId | integer | The unique identifier of the company to which the company notes belong                                            |
| perPage   | integer | The number of company notes to fetch                                                                              |
| start     | integer | The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.) |

{% tabs %}
{% tab title="200 " %}
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
            "companyId": 4,
            "noteText": "<p>Company Note 1</p>\n",
            "createdByUserId": 1,
            "createdDate": "2022-06-12 06:06:03 UTC",
            "modifiedDate": "2022-07-13 01:32:10"
        },
        {
            "id": 4,
            "companyId": 4,
            "noteText": "<p>Company Note 2</p>\n",
            "createdByUserId": 1,
            "createdDate": "2022-07-13 01:27:27 UTC",
            "modifiedDate": "2022-07-13 01:27:27"
        },
        {
            "id": 5,
            "companyId": 4,
            "noteText": "<p>Company Note 3</p>\n",
            "createdByUserId": 1,
            "createdDate": "2022-07-13 01:29:41 UTC",
            "modifiedDate": "2022-07-13 01:29:41"
        },
    ]
}

```
{% endtab %}
{% endtabs %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of company note to which the user has access. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Fetches a list of Notes for a specific Company`

```javascript
{
    "companyId" : 4,
    "perPage" : 50
}
```

## Company Note

| Property        | Type      | Description                                             |
| --------------- | --------- | ------------------------------------------------------- |
| id              | integer   | The unique id of the company note                       |
| companyId       | integer   | The id of the company to which the company note belongs |
| noteText        | string    | The company note                                        |
| createdByUserId | integer   | The details of person who created the company note      |
| createdDate     | timestamp | The date & time the company note was created            |
| modifiedDate    | timestamp | The date & time the company note was last modified      |
