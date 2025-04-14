# Get Event Type List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="venue?action=getEventTypeList" %}
{% api-method-summary %}
Get Venue Event Types List
{% endapi-method-summary %}

{% api-method-description %}
Return the event type list for the account.
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
        "totalResults": 11,
        "start": 0,
        "perPage": 2,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "name": "Christmas",
            "description": null,
            "marketplaceEventType": 11,
            "contactType": 0,
            "isViewable": true,
            "createdDate": "2017-12-18 09:48:05 UTC",
            "modifiedDate": "2017-12-18 09:48:05 UTC"
        },
        {
            "id": 2,
            "name": "Cocktail",
            "description": null,
            "marketplaceEventType": 11,
            "contactType": 0,
            "isViewable": true,
            "createdDate": "2017-12-18 09:48:05 UTC",
            "modifiedDate": "2017-12-18 09:48:05 UTC"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get Venues Event Type List`

```javascript
{
"perPage": 10
"start": 0
}
```

## Returns

`A collection object with the following properties in the results`

| Property | Description |
| :--- | :--- |
| id | The unique invoice identifier |
| name | The name of the event type |
| description | The description of the event type |
| marketplaceEventType | The Venue Marketplace event type to associate with the event type. See [Marketplace Event Types](get-event-type-list.md.md#marketplace-event-types) |
| contactType | The type of contact that can be assigned to a opportunity/booking of the event type. 0 = Company & Contact, 1 = Company, 2 = Contact |
| isViewable | Whether or not the event type  is viewable on marketplace |
| createdDate | The date & time the event type  was created |
| modifiedDate | The date & time the event type  was last modified |

## Marketplace Event Types

| \# | Description |
| :--- | :--- |
| 2 | Christmas |
| 3 | Cocktail |
| 4 | Conference |
| 5 | Corporate Function |
| 13 | Breakfast |
| 14 | Lunch |
| 6 | Dinner |
| 11 | Event |
| 7 | Exhibition |
| 8 | Meeting |
| 9 | Party |
| 10 | Wedding |
| 1 | Other |

