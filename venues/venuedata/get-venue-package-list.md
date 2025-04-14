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
        "totalResults": 19,
        "start": 0,
        "perPage": 2,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "name": "Day Delegate Package",
            "type": 1,
            "minPax": 1,
            "maxPax": 0,
            "cost": 500,
            "priceMethod": 2,
            "actualCost": 40,
            "actualCostExcludedTaxIds": [
                1,
                6064,
                6146,
                6221,
                6226,
                6227,
                6262,
                6263,
                6264
            ],
            "smallDescription": "Includes Room Hire, Morning Tea,\nLunch, Afternoon Tea and basic AV equiptment",
            "largeDescription": "<p>Includes Room Hire, Morning Tea,<br />\nLunch, Afternoon Tea and basic AV equiptmentIncludes Room Hire, Morning Tea,<br />\nLunch, Afternoon Tea and basic AV equiptmentIncludes Room Hire, Morning Tea,<br />\nLunch, Afternoon Tea and basic AV equiptmentIncludes Room Hire, Morning Tea,<br />\nLunch, Afternoon Tea and basic AV equiptmentIncludes Room Hire, Morning Tea,<br />\nLunch, Afternoon Tea and basic AV equiptmentIncludes Room Hire, Morning Tea,<br />\nLunch, Afternoon Tea and basic AV equiptment</p>\n",
            "marketplaceName": "Day Delegate Package",
            "isVisibleOnVenueSearch": true,
            "createdDate": "2015-01-23 07:54:46",
            "modifiedDate": "2025-03-27 23:56:02",
            "startDate": null,
            "endDate": null,
            "startTime": "09:00:00",
            "endTime": "15:00:00",
            "costcenters": [
                {
                    "costcenterId": 1,
                    "value": 0
                },
                {
                    "costcenterId": 2,
                    "value": 100
                },
                {
                    "costcenterId": 3,
                    "value": 100
                },
                {
                    "costcenterId": 4,
                    "value": 100
                },
                {
                    "costcenterId": 5,
                    "value": 100
                },
                {
                    "costcenterId": 7,
                    "value": 100
                },
                {
                    "costcenterId": 32,
                    "value": 0
                },
                {
                    "costcenterId": 33,
                    "value": 0
                },
                {
                    "costcenterId": 966,
                    "value": 0
                },
                {
                    "costcenterId": 8389,
                    "value": 0
                },
                {
                    "costcenterId": 8390,
                    "value": 0
                },
                {
                    "costcenterId": 16235,
                    "value": 0
                },
                {
                    "costcenterId": 16236,
                    "value": 0
                }
            ],
            "hasSessions": true,
            "spaceId": 1,
            "spaceLayoutId": 0,
            "spaceCustomLayoutName": "Custom layout",
            "sortOrder": 1,
            "excludedFromCommissions": false,
            "reduceRoomHireFirst": false,
            "eventTypes": [
                14,
                2
            ],
            "userGroupIds": [],
            "hasLimitedStartTimes": true,
            "limitedStartTimes": [
                "00:30:00",
                "01:00:00",
                "05:30:00"
            ],
            "isAccommIncluded": false,
            "discountCampaignId": 2,
            "costcentersDiscounts": []
        },
        {
            "id": 2146,
            "name": "Day Delegate Package (*Copy*)",
            "type": 1,
            "minPax": 1,
            "maxPax": 0,
            "cost": 500,
            "priceMethod": 2,
            "actualCost": 40,
            "actualCostExcludedTaxIds": [
                1,
                6064,
                6146,
                6221,
                6226,
                6227,
                6262,
                6263,
                6264
            ],
            "smallDescription": "Includes Room Hire, Morning Tea,\nLunch, Afternoon Tea and basic AV equiptment",
            "largeDescription": "<p>Includes Room Hire, Morning Tea,<br />\nLunch, Afternoon Tea and basic AV equiptmentIncludes Room Hire, Morning Tea,<br />",
            "marketplaceName": "Day Delegate Package",
            "isVisibleOnVenueSearch": false,
            "createdDate": "2023-12-14 06:59:05",
            "modifiedDate": "2023-12-14 06:59:05",
            "startDate": null,
            "endDate": null,
            "startTime": "09:00:00",
            "endTime": "15:00:00",
            "costcenters": [
                {
                    "costcenterId": 1,
                    "value": 0
                },
                {
                    "costcenterId": 2,
                    "value": 100
                },
                {
                    "costcenterId": 3,
                    "value": 100
                },
                {
                    "costcenterId": 4,
                    "value": 100
                },
                {
                    "costcenterId": 5,
                    "value": 100
                },
                {
                    "costcenterId": 7,
                    "value": 100
                },
                {
                    "costcenterId": 32,
                    "value": 0
                },
                {
                    "costcenterId": 33,
                    "value": 0
                },
                {
                    "costcenterId": 966,
                    "value": 0
                },
                {
                    "costcenterId": 8389,
                    "value": 0
                },
                {
                    "costcenterId": 8390,
                    "value": 0
                },
                {
                    "costcenterId": 16235,
                    "value": 0
                },
                {
                    "costcenterId": 16236,
                    "value": 0
                }
            ],
            "hasSessions": true,
            "spaceId": 1,
            "spaceLayoutId": 0,
            "spaceCustomLayoutName": "Custom layout",
            "sortOrder": 1,
            "excludedFromCommissions": true,
            "reduceRoomHireFirst": false,
            "eventTypes": [
                14,
                2
            ],
            "userGroupIds": [],
            "hasLimitedStartTimes": false,
            "limitedStartTimes": [],
            "isAccommIncluded": false,
            "discountCampaignId": 0,
            "costcentersDiscounts": []
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
| type                         | enum        | Simple or Detailed                                                                            |
| minPax                       | integer     | The minimum pax of the package                                                               |
| maxPax                       | integer     | The maximum pax of the package                                                               |
| cost                         | float       | The price of the package (depends on the "priceMethod" value)                                 |
| priceMethod                  | enum        | The type of package price - per person or flat rate                                           |
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
| costcenters                  | array       | The cost centers to which the package applies. see                                                |
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
| costcentersDiscounts         | array       | The cost center discounts to apply to the package                                           |


## Cost Centers

| Property       | Data Type | Description                                |
|----------------|-----------|--------------------------------------------|
| costcenterId   | integer   | The cost center identifier                |
| value          | float     | The discount percentage for the cost center |


## Cost Center Discounts

| Property       | Data Type | Description                     |
|----------------|-----------|---------------------------------|
| costcenterId   | integer   | The cost center identifier     |
| value          | float     | The price for the cost center  |

## Package Type

| Identifier       | Description                     |
|----------------|---------------------------------|
| 1   | Detailed     |
| 2          | Simple  |

## Price Method
| Identifier       | Description                     |
|----------------|---------------------------------|
| 1   | Per Person     |
| 2          | Flat Rate  |



The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.