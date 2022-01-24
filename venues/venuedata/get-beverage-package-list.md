# Get Beverage Package List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getBeveragePackageList" method="post" summary="Get Beverage Package List" %}
{% swagger-description %}
Get a list of Beverage Packages.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of beverage package to get in a single call
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
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
            "name": "Beverage Package 2",
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
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the beverages the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific Beverage Package List`

```javascript
{
  "venueId": "1",
  "perPage": "50",
}
```

## Beverage Package

| Property              | Type                                                                                   | Description                                                                                 |
| --------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| id                    | integer                                                                                | The unique id of the Beverage Package                                                       |
| name                  | text                                                                                   | The name of the Beverage Package                                                            |
| minimumPax            | integer                                                                                | The minimum number of people allowed within a single session to order this Beverage Package |
| maximumPax            | integer                                                                                | The maximum number of people allowed within a single session to order this Beverage Package |
| price                 | integer                                                                                | The price of the Beverage Package                                                           |
| cost | double | The price of the Beverage Package |
| costs | array [Hourly Cost](get-beverage-package-list.md#hourly-cost)  | The hourly cost details of the beverage package |
| actualCost | double | The price of the Beverage Package |
| priceType             | integer [Price Type](get-beverage-package-list.md#price-type-beverage-package-pricing) | The price type of the Beverage Package                                                      |
| smallDescription      | text                                                                                   | The small description of the Beverage Package                                               |
| marketplaceName       | text                                                                                   | The name of the Beverage Package displayed in marketplace booking engines                   |
| marketplaceEventTypes | text                                                                                   | The event types of the Beverage Package displayed in marketplace booking engines            |

## Price Type (Beverage Package pricing)

One of the following values:

* 1 = Per person
* 2 = Flat rate

## Hourly Cost \(Hourly Cost\)
| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the Beverage Package Hourly Cost|
| beveragePackageId | integer | The unique id of the Beverage Package Hourly Cost|
| id | integer | The unique id of the Beverage Package Hourly Cost|
| beveragePackageId | integer | The unique identifier of the Beverage Package|
| numHours | integer | The number of hours for which the cost apply|
| cost | double | The hourly cost of the Beverage Package for this setup|
| costExcludedTaxIds | double | The cost excluded tax identifiers|
| actualCost | double | The actual hourly cost of the Beverage Package for this setup|
| actualCostExcludedTaxIds | double | The actual cost excluded tax identifiers|