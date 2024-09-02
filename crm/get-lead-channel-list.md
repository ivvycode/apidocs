# Get Lead Channel List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="crm?action=getLeadChannelList" %}
{% api-method-summary %}
Get Lead Channel List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of lead channels.
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
        "count": 4
    },
    "results": [
        {
            "id": 1,
            "name": "iVvy Marketplace"
        },
        {
            "id": 2,
            "name": "Website Booking Engine"
        },
        {
            "id": 3,
            "name": "Third Party Booking Engines"
        },
        {
            "id": 4,
            "name": "Magazine Ad"
        },
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the lead channels the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

