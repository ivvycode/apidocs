# Get Space Hire Plan Rate

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getSpaceHirePlanRate" method="post" summary="Get Space Hire Plan Rate" %}
{% swagger-description %}
Return the detailed space rates for the specific space hire plan.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="tariffId" type="integer" in="path" %}
The id of the space hire plan
{% endswagger-parameter %}

{% swagger-parameter name="tariffRateId" type="integer" in="path" %}
The id of the space hire plan rate
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "id": 9,
    "venueId": 1,
    "tariffId": 8,
    "colour": "#e4afaf",
    "startDate": "2021-01-09",
    "endDate": "2021-01-16",
    "daysOfWeek": [
        0,
        1
    ],
    "createdDate": "2021-01-08 12:01:22 UTC",
    "modifiedDate": "2022-10-24 07:57:22 UTC",
    "spaceRates": [
        {
            "id": 8,
            "spaceId": 1,
            "spaceName": "Space",
            "minSpendCost": 200,
            "hourlyCost": 100,
            "halfDayCost": 50,
            "halfDayCostMinMins": 75,
            "halfDayCostMaxMins": 240,
            "halfDayCostAvailFrom": "19:30:00",
            "halfDayCostAvailTo": "20:00:00",
            "fullDayCost": 60,
            "fullDayCostMinMins": 75,
            "fullDayCostMaxMins": 150,
            "fullDayCostAvailFrom": "10:30:00",
            "fullDayCostAvailTo": "13:00:00",
            "nightCost": 60,
            "nightCostMinMins": 60,
            "nightCostMaxMins": 180,
            "nightCostAvailFrom": "22:00:00",
            "nightCostAvailTo": "23:00:00",
            "areCostsPerPerson": true,
            "hasLayoutRates": false,
            "createdDate": "2022-10-20 07:32:11 UTC",
            "modifiedDate": "2022-10-21 01:16:34 UTC"
        },
        {
            "id": 9,
            "spaceId": 3,
            "spaceName": "PRO - The Salon",
            "minSpendCost": 40,
            "hourlyCost": 0,
            "halfDayCost": 0,
            "halfDayCostMinMins": 0,
            "halfDayCostMaxMins": 0,
            "halfDayCostAvailFrom": null,
            "halfDayCostAvailTo": null,
            "fullDayCost": 0,
            "fullDayCostMinMins": 0,
            "fullDayCostMaxMins": 0,
            "fullDayCostAvailFrom": null,
            "fullDayCostAvailTo": null,
            "nightCost": 0,
            "nightCostMinMins": 0,
            "nightCostMaxMins": 0,
            "nightCostAvailFrom": null,
            "nightCostAvailTo": null,
            "areCostsPerPerson": false,
            "hasLayoutRates": false,
            "createdDate": "2022-10-21 01:07:10 UTC",
            "modifiedDate": "2022-10-21 01:07:10 UTC"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Space Hire Plan Rate`

```javascript
{
  "venueId": 1,
  "tariffId": 8,
  "tariffRateId": 9,
}
```

## Returns

| Property                    | Data Type | Description                                                                                                                                                                                                                              |
| --------------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id | int | The unique identifier of the tariff rate |
| venueId | int | The venue identifier of the tariff rate |
| tariffId | int | The unique identifier of the tariff |
| colour |  string |  The colour to identify the tariff rate |
| startDate | sqldate |The start date of tariff rate |
| endDate | sqldate | The end date of tariff rate |
| spaceRates | array | The detailed rates for each spaces for the tariff rate. See [Space Rate](get-space-hire-plan-rate.md#space-rate)|
| daysOfWeek |  array | The days of the week to which the tariff rate applies |
| createdDate | timestamp | The date & time the tariff rate was created |
| modifiedDate | timestamp | The date & time the tariff rate was last modified |

## daysOfWeek:

following values:

* 0 = Sunday
* 1 = Monday
* 2 = Tuesday
* 3 = Wednesday
* 4 = Thursday
* 5 = Friday
* 6 = Saturday


## Space Rate

| Property                    | Data Type | Description  |
| --------------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id | string | The uniqie identifier of the tariff space rate |
| spaceId | int | The space id of the tariff space rate |
| spaceName | string | The space name of the tariff space rate |
| minSpendCost | number | The minimum Sale Price of the tariff space rate |
| minSpendCostExcludedTaxIds | array | The minimum Sale Price ExcludedTaxIds of the tariff space rate |
| hourlyCost | number | The hourly sale Price of the tariff space rate |
| hourlyCostExcludedTaxIds | array | The hourly sale Price ExcludedTaxIds of the tariff space rate |
| halfDayCost | number | The Half Day Sale Price of the tariff space rate |
| halfDayCostExcludedTaxIds | array | The Half Day Sale Price ExcludedTaxIds of the tariff space rate |
| halfDayCostMinMins | int | The Half Day minimum minutes of the tariff space rate |
| halfDayCostMaxMins | int | The Half Day maximum minutes of the tariff space rate |
| halfDayCostAvailFrom | string | The Half Day Available From of the tariff space rate |
| halfDayCostAvailTo | string | The Half Day Available To of the tariff space rate |
| fullDayCost | number | The fullDayCost of the tariff space rate |
| fullDayCostExcludedTaxIds | array | The fullDayCostExcludedTaxIds of the tariff space rate |
| fullDayCostMinMins | int | The full day minimum minutes of the tariff space rate |
| fullDayCostMaxMins | int | The full day maximum minutes of the tariff space rate |
| fullDayCostAvailFrom | string | The full day  Available From of the tariff space rate |
| fullDayCostAvailTo | string | The full day Available To of the tariff space rate |
| nightCost | number | The night sale price of the tariff space rate |
| nightCostExcludedTaxIds | array | The night sale price ExcludedTaxIds of the tariff space rate |
| nightCostMinMins | int | The n minimum minutes of the tariff space rate |
| nightCostMaxMins | int | The night maximum minutes of the tariff space rate |
| nightCostAvailFrom | string | The night Available From of the tariff space rate |
| nightCostAvailTo | string | The night Available To of the tariff space rate |
| areCostsPerPerson | boolean | Whether costs are per person for the tariff space rate |
| hasLayoutRates | boolean | Whether or not layout has rates for the tariff space rate |
| createdDate | timestamp | The createdDate of the tariff space rate |
| modifiedDate | timestamp | The modifiedDate of the tariff space rate |