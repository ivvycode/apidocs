# Get Industry List

{% swagger baseUrl="[PlatformAddress]/api/1.0" path="account?action=getIndustryList" method="post" summary="Get Industry List" %}
{% swagger-description %}
Fetches the list of industries in the account.
{% endswagger-description %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of industries to get in a single api call. max is 100.
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="path" %}
The starting result of the page. Note this is zero based (i.e. sending start = 0 will start from the first result.)
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 26,
        "start": 0,
        "perPage": 100,
        "count": 26
    },
    "results": [
        {
            "id": 46157,
            "name": "Advertising & Marketing",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46158,
            "name": "Agricultural, Forestry, Horticulture",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46159,
            "name": "Association",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46160,
            "name": "Automotive",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46161,
            "name": "Charity, Religious & Welfare",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46162,
            "name": "Construction, Engineering & Trades",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46163,
            "name": "Consultants",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46164,
            "name": "Corporate Travel Agent",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46165,
            "name": "Education",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46166,
            "name": "Entertainment",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46167,
            "name": "Fashion",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46168,
            "name": "Finance",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46169,
            "name": "Government",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46170,
            "name": "Healthcare & Pharma",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46171,
            "name": "Internal",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46172,
            "name": "Insurance",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46173,
            "name": "IT/Telco",
            "createdDate": "2019-01-29 23:12:20 UTC",
            "modifiedDate": "2019-01-29 23:12:20 UTC"
        },
        {
            "id": 46174,
            "name": "Legal",
            "createdDate": "2019-01-29 23:12:21 UTC",
            "modifiedDate": "2019-01-29 23:12:21 UTC"
        },
        {
            "id": 46175,
            "name": "Manufacturing",
            "createdDate": "2019-01-29 23:12:21 UTC",
            "modifiedDate": "2019-01-29 23:12:21 UTC"
        },
        {
            "id": 46176,
            "name": "Mining",
            "createdDate": "2019-01-29 23:12:21 UTC",
            "modifiedDate": "2019-01-29 23:12:21 UTC"
        },
        {
            "id": 46177,
            "name": "Real Estate",
            "createdDate": "2019-01-29 23:12:21 UTC",
            "modifiedDate": "2019-01-29 23:12:21 UTC"
        },
        {
            "id": 46178,
            "name": "Retail",
            "createdDate": "2019-01-29 23:12:21 UTC",
            "modifiedDate": "2019-01-29 23:12:21 UTC"
        },
        {
            "id": 46179,
            "name": "Sporting & Recreation",
            "createdDate": "2019-01-29 23:12:21 UTC",
            "modifiedDate": "2019-01-29 23:12:21 UTC"
        },
        {
            "id": 46180,
            "name": "Transportation",
            "createdDate": "2019-01-29 23:12:21 UTC",
            "modifiedDate": "2019-01-29 23:12:21 UTC"
        },
        {
            "id": 46181,
            "name": "Wedding",
            "createdDate": "2019-01-29 23:12:21 UTC",
            "modifiedDate": "2019-01-29 23:12:21 UTC"
        },
        {
            "id": 51031,
            "name": "ecommerce",
            "createdDate": "2024-08-15 04:44:40 UTC",
            "modifiedDate": "2024-08-15 04:44:40 UTC"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Returns

| Property      | Description                                                                                |
| ------------- | ------------------------------------------------------------------------------------------ |
| id            | The unique identifier for the industry                                                     |
| name          | The name of the industry                                                                   |
| createdDate   | The date & time the industry was created                                                   |
| modifiedDate  | The date & time the industry was last modified                                            |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the users. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.
