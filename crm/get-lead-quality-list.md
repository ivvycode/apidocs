# Get Lead Quality List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="crm?action=getLeadQualityList" %}
{% api-method-summary %}
Get Lead Quality List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of lead qualities.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 10,
        "count": 3
    },
    "results": [
        {
            "id": 1,
            "label": "A-Grade",
            "showOnDash": true
        },
        {
            "id": 2,
            "label": "B-Grade",
            "showOnDash": false
        },
        {
            "id": 3,
            "label": "C-Grade",
            "showOnDash": false
        },
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the lead qualities the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

