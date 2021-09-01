# Get Beverage Package List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getBeveragePackageList" path="" %}
{% api-method-summary %}
Get Beverage Package List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of beverage packages.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=false %}
The number of beverage package to get in a single call
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
            "name": "Beverage Package 1",
            "minPax": 20,
            "maxPax": 30,
            "price": 98,
            "priceMethod": 100,
            "smallDescription": "small description",
            "marketplaceName": "Marketplace Name 1",
            "marketplaceCategories": [3, 5]
        },
        {   
            "id": 125,
            "name": "Beverage Package 2",
            "minPax": 10,
            "maxPax": 30,
            "price": 198,
            "priceMethod": 102,
            "smallDescription": "small description",
            "marketplaceName": "Marketplace Name 2",
            "marketplaceCategories": []
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the beverages the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

```javascript
{
  "venueId": 1,
  "perPage": 50,
  "start": 40
}
```

## Beverage Package

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the Beverage Package |
| name | text | The name of the Beverage Package |
| minPax | integer | The minimum number of people allowed within a single session to order this Beverage Package |
| maxPax | integer | The maximum number of people allowed within a single session to order this Beverage Package |
| price | float | The price of the Beverage Package |
| priceMethod | integer [Price Method](get-beverage-package-list.md#price-method-beverage-package-pricing) | The price type of the Beverage Package |
| smallDescription | text | The small description of the Beverage Package |
| marketplaceName | text | The name of the Beverage Package displayed in marketplace booking engines |
| marketplaceCategories | array of [Marketplace Categories](get-menu-list.md#marketplace-categories) | The categories in which the Beverage Package will be displayed in marketplace booking engines |

## Price Method \(Beverage Package Pricing\)

* 99 = Hourly rate
* 100 = Per person
* 102 = Fixed rate
* 103 = Total of package items

