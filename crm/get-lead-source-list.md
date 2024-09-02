# Get Lead Source List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="crm?action=getLeadSourceList" %}
{% api-method-summary %}
Get Lead Source List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of lead sources.
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
        "totalResults": 6,
        "start": 0,
        "perPage": 100,
        "count": 5
    },
     "results": [
        {
            "id": 1,
            "name": "iVvy Marketplace",
            "description": null,
            "cost": 0,
            "isReferral": false,
            "defaultType": null
        },
        {
            "id": 2,
            "name": "Website Widget",
            "description": null,
            "cost": 0,
            "isReferral": false,
            "defaultType": null
        },
        {
            "id": 3,
            "name": "Google",
            "description": "",
            "cost": 1,
            "isReferral": false,
            "defaultType": null
        },
        {
            "id": 4,
            "name": "Third Party Websites",
            "description": null,
            "cost": 0,
            "isReferral": false,
            "defaultType": null
        },
        {
            "id": 189,
            "name": "Referral Program",
            "description": null,
            "cost": 0,
            "isReferral": false,
            "defaultType": 1
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the lead stages the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

