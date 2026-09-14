# Get Lead Note List

## Get Lead Note List

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/crm?action=getLeadNoteList`

Fetches a list of notes for a specific lead.

#### Path Parameters

| Name    | Type    | Description                                                                                                       |
| ------- | ------- | ----------------------------------------------------------------------------------------------------------------- |
| leadId  | integer | The unique identifier of the lead to which the lead notes belong                                                  |
| perPage | integer | The number of lead notes to fetch                                                                                 |
| start   | integer | The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.) |

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
            "leadId": 4,
            "note": "<p>Lead Note 1</p>\n",
            "createdByUserId": 1,
            "createdDate": "2022-06-12 06:06:03 UTC",
            "modifiedDate": "2022-07-13 01:32:10"
        },
        {
            "id": 4,
            "leadId": 4,
            "note": "Lead Note 2",
            "createdByUserId": 1,
            "createdDate": "2022-07-13 01:27:27 UTC",
            "modifiedDate": "2022-07-13 01:27:27"
        },
        {
            "id": 5,
            "leadId": 4,
            "note": "Lead Note 3",
            "createdByUserId": 1,
            "createdDate": "2022-07-13 01:29:41 UTC",
            "modifiedDate": "2022-07-13 01:29:41"
        },
    ]
}

```
{% endtab %}
{% endtabs %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of lead note to which the user has access. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Fetches a list of Notes for a specific Lead`

```javascript
{
    "leadId" : 4,
    "perPage" : 50
}
```

## Lead Note

| Property        | Type      | Description                                     |
| --------------- | --------- | ----------------------------------------------- |
| id              | integer   | The unique id of the lead note                  |
| leadId          | integer   | The leads to which the lead note belongs        |
| note            | string    | The lead note                                   |
| createdByUserId | integer   | The details of person who created the lead note |
| createdDate     | timestamp | The date & time the lead note was created       |
| modifiedDate    | timestamp | The date & time the lead note was last modified |
