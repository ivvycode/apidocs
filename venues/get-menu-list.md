# Get Menus

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getMenuList" path="" %}
{% api-method-summary %}
Get Menu List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of menus.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=false %}
The number of menu to get in a single call
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 5,
        "start": 0,
        "perPage": 50,
        "count": 2
    },
    "results": [
        {
            "id": 125,
            "name": "Menu 1",
            "minimumPax": 20,
            "maximumPax": 30,
            "cost": 98,
            "costType": 1,
            "smallDescription": "small description",
            "marketplaceName": "Marketplace Name 1",
            "marketplaceEventTypes": null
        },
        {   
            "id": 125,
            "name": "Menu 2",
            "minimumPax": 10,
            "maximumPax": 30,
            "cost": 198,
            "costType": 2,
            "smallDescription": "small description",
            "marketplaceName": "Marketplace Name 2",
            "marketplaceEventTypes": null
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific menu List`

```javascript
{
  "venueId": "1",
  "perPage": "50",
}
```

## Menu

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the menu |
| name | text | The name of the menu |
| minimumPax | integer | The minimum number of people allowed within a single session to order this menu |
| maximumPax | integer | The maximum number of people allowed within a single session to order this menu |
| cost | integer | The price of the menu |
| costType | integer [Cost Type](get-menu-list.md#cost-type-menu-pricing) | The price type of the menu |
| smallDescription | text | The small description of the menu |
| marketplaceName | text | The name of the menu displayed in marketplace booking engines |
| marketplaceEventTypes | text | The event types of the menu displayed in marketplace booking engines |

## Cost Type \(menu pricing\)

One of the following values:

* 1 = Per person
* 2 = Flat rate

