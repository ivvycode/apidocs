# Get Venue Package (Event Template) List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getVenuePackageList" method="post" summary="Get Venue Package (Event Template) List" %}
{% swagger-description %}
Provides the list of packages (Event Templates)
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 100,
        "count": 1
    },
    "results": [
        {
            "id": 1,
            "name": "Standard",
            "type": 1,
            "minPax": 1,
            "maxPax": 1000,
            "cost": 500,
            "priceMethod": 1,
            "actualCost": 50,
            "actualCostExcludedTaxIds": [
                1,
                317,
                1046,
                1203,
                1204,
                1955,
                1986,
                1988,
                3910,
                3979
            ],
            "smallDescription": "Standard",
            "largeDescription": "<p>Standard</p>\n",
            "marketplaceName": "Standard",
            "isVisibleOnVenueSearch": false,
            "createdDate": "2017-12-18 12:23:53",
            "modifiedDate": "2025-04-23 23:28:28",
            "startDate": null,
            "endDate": null,
            "startTime": "06:00:00",
            "endTime": "12:30:00",
            "costcenters": [
                {
                    "id": 1,
                    "value": 149.5,
                    "excludedTaxIds": [
                        1,
                        317,
                        1955
                    ]
                },
                {
                    "id": 2,
                    "value": 100,
                    "excludedTaxIds": []
                },
                {
                    "id": 3,
                    "value": 100.5,
                    "excludedTaxIds": [
                        3910,
                        3979
                    ]
                },
                {
                    "id": 4,
                    "value": 100,
                    "excludedTaxIds": []
                },
                {
                    "id": 5,
                    "value": 0,
                    "excludedTaxIds": []
                },
                {
                    "id": 1166,
                    "value": 0,
                    "excludedTaxIds": []
                },
                {
                    "id": 2986,
                    "value": 50,
                    "excludedTaxIds": []
                },
                {
                    "id": 6338,
                    "value": 0,
                    "excludedTaxIds": []
                },
                {
                    "id": 17647,
                    "value": 0,
                    "excludedTaxIds": []
                },
                {
                    "id": 17648,
                    "value": 0,
                    "excludedTaxIds": []
                },
                {
                    "id": 17649,
                    "value": 0,
                    "excludedTaxIds": []
                }
            ],
            "hasSessions": true,
            "spaceId": 1,
            "spaceLayoutId": 2,
            "spaceCustomLayoutName": "C",
            "sortOrder": 0,
            "excludedFromCommissions": false,
            "reduceRoomHireFirst": true,
            "eventTypes": [
                1,
                2,
                3,
                4,
                5,
                6
            ],
            "userGroupIds": [
                1,
                2
            ],
            "hasLimitedStartTimes": true,
            "limitedStartTimes": [
                "02:30:00",
                "03:00:00"
            ],
            "isAccommIncluded": true,
            "discountCampaignId": 59,
            "costcentersDiscounts": [
                {
                    "id": 1,
                    "value": 18
                },
                {
                    "id": 2,
                    "value": 18
                },
                {
                    "id": 3,
                    "value": 18
                },
                {
                    "id": 4,
                    "value": 18
                },
                {
                    "id": 5,
                    "value": 18
                },
                {
                    "id": 6338,
                    "value": 18
                },
                {
                    "id": 2986,
                    "value": 18
                }
            ]
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`getVenuePackageList`

```javascript
{
    "venueId": 1,
    "perPage": 2
}
```

## Returns

`A collection object with the following properties in the results`

| Property                     | Data Type   | Description                                                                                     |
|------------------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                           | integer     | The unique identifier of the package                                                          |
| name                         | string      | The name of the package                                                                       |
| type                         | enum [PackageType](get-venue-package-list.md#package-type)        | Simple or Detailed                      |
| minPax                       | integer     | The minimum pax of the package                                                               |
| maxPax                       | integer     | The maximum pax of the package                                                               |
| cost                         | float       | The price of the package (depends on the "priceMethod" value)                                 |
| priceMethod                  | enum [priceMethod](get-venue-package-list.md#price-method)       | The type of package price - per person or flat rate |
| actualCost                   | float       | The actual cost of the package                                                               |
| actualCostExcludedTaxIds     | array       | The tax ids excluded from the actual cost                                                    |
| smallDescription             | string      | A html formatted small description of the package                                            |
| largeDescription             | string      | A html formatted large description of the package                                            |
| marketplaceName              | string      | The name of the package displayed in marketplace booking engines                             |
| isVisibleOnVenueSearch       | boolean     | Whether the package is visible on venue search                                               |
| createdDate                  | datetime    | The date and time the package was created                                                   |
| modifiedDate                 | datetime    | The date and time the package was last modified. Does not include changes to the package items |
| startDate                    | date        | The date from which the package is available                                                |
| endDate                      | date        | The date to which the package is available                                                  |
| startTime                    | time        | The time from which the package is available                                                |
| endTime                      | time        | The time to which the package is available                                                  |
| costcenters                  | array of [CostCenter](get-venue-package-list.md#cost-center) | The cost centers to which the package applies.|
| hasSessions                  | boolean     | Whether the package has sessions                                                            |
| spaceId                      | integer     | The default space to be used for the package                                                |
| spaceLayoutId                | integer     | The default space layout to be used for the package                                         |
| spaceCustomLayoutName        | string      | Layout name for custom space layout                                                         |
| sortOrder                    | integer     | The order in which the package should be displayed                                          |
| excludedFromCommissions      | boolean     | Whether the package is excluded from commissions                                            |
| reduceRoomHireFirst          | boolean     | Whether to reduce room hire first when applying the package to bookings                     |
| eventTypes                   | array       | The marketplace event types to which the package applies. If empty, the package applies to all event types |
| userGroupIds                 | array       | The user groups to which the package applies. If empty, the package applies to all user groups |
| hasLimitedStartTimes         | boolean     | Whether the package has limited start times                                                 |
| limitedStartTimes            | time        | The limited start time of the package                                                       |
| isAccommIncluded             | boolean     | Whether accommodation is included in the package. This is a legacy field and should not be used |
| discountCampaignId           | integer     | The discount campaign to apply to the package                                               |
| costcentersDiscounts         | array of [Cost Center Discounts](get-venue-package-list.md#cost-center-discount)       | The cost center discounts to apply to the package |


## Cost Center

| Property       | Data Type | Description                                |
|----------------|-----------|--------------------------------------------|
| id   | integer   | The cost center identifier                |
| value          | float     | The discount percentage for the cost center |


## Cost Center Discount

| Property       | Data Type | Description                     |
|----------------|-----------|---------------------------------|
| id             | integer   | The cost center identifier     |
| value          | float     | The price for the cost center  |

## Package Type

| Identifier | Description |
|------------|-------------|
| 1          | Detailed    |
| 2          | Simple      |

## Price Method

| Identifier | Description |
|------------|-------------|
| 1          | Per Person  |
| 2          | Flat Rate   |



The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.