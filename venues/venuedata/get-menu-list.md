# Get Menu List

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
            "menuTypeCategory": 0,
            "name": "Menu 1",
            "minimumPax": 20,
            "maximumPax": 30,
            "cost": 98,
            "costType": 1,
            "smallDescription": "small description",
            "marketplaceName": "Marketplace Name 1",
            "marketplaceCategories": []
        },
        {   
            "id": 125,
            "menuTypeCategory": 1,
            "name": "Menu 2",
            "minimumPax": 10,
            "maximumPax": 30,
            "cost": 198,
            "costType": 2,
            "smallDescription": "small description",
            "marketplaceName": "Marketplace Name 2",
            "marketplaceCategories": [3]
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the menus the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

```javascript
{
  "venueId": 1,
  "perPage": 50,
  "start": 15
}
```

## Menu

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the menu |
| menuTypeCategory | integer [Menu Type Category](get-menu-list.md#menu-type-categories) | The category of the menu type that's used in various reports |
| name | text | The name of the menu |
| minimumPax | integer | The minimum number of people allowed within a single session to order this menu |
| maximumPax | integer | The maximum number of people allowed within a single session to order this menu |
| cost | integer | The price of the menu |
| costType | integer [Cost Type](get-menu-list.md#cost-type-menu-pricing) | The price type of the menu |
| smallDescription | text | The small description of the menu |
| marketplaceName | text | The name of the menu displayed in marketplace booking engines |
| marketplaceCategories | array of [Marketplace Categories](get-menu-list.md#marketplace-categories) | The categories in which the menu will be displayed in marketplace booking engines |

## Cost Type \(Menu Pricing\)

* 1 = Per person
* 2 = Flat rate
* 3 = Total of menu items

## Marketplace Categories

* 1 = Breakfast
* 2 = Morning Break
* 3 = Lunch
* 4 = Afternoon Break
* 5 = Dinner
* 6 = Cocktail

## Menu Type Categories

* 1 = Breakfast
* 2 = Lunch
* 3 = Dinner
* 4 = Coffee Break
* 5 = Reception
* 6 = Outside Catering



