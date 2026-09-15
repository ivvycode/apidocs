# Get Space Hire Plans

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/venue?action=getSpaceHirePlanList`

Get a list of space hire plans.

#### Path Parameters

| Name                                      | Type    | Description                                           |
| ----------------------------------------- | ------- | ----------------------------------------------------- |
| venueId<mark style="color:red;">\*</mark> | integer | The id of the venue                                   |
| perPage                                   | integer | The number of space hire plan to get in a single call |

{% tabs %}
{% tab title="200 " %}
```
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 50,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "name": "RHP",
            "code": "RHP",
            "description": null,
            "createdDate": "2017-12-18 12:17:49 UTC",
            "modifiedDate": "2018-01-15 05:44:41 UTC"
        },
        {
            "id": 8,
            "name": "Test Hire Plan",
            "code": "HIRE123",
            "description": "<p>test</p> ",
            "createdDate": "2019-04-03 11:27:42 UTC",
            "modifiedDate": "2020-04-29 04:43:02 UTC"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the space hire plans the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

### Example Request

`Get a specific space hire plan list`

```javascript
{
  "venueId": "1",
  "perPage": "50",
}
```
