# Get Venue Package Details

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getVenuePackage" method="post" summary="Return the all details of the package including its items" %}
{% swagger-description %}
Provides all the details of the venue package including Sessions and its items ie. Menus, Beverages, Resources, Products, Setup Requirements and Setup Requirement Options
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="body" %}
The id of the venue package
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
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
    ],
    "sessions": [
        {
            "id": 1,
            "name": "Morning1",
            "startTime": "08:00:00",
            "endTime": "09:00:00",
            "setupTime": 0,
            "setDownTime": 0,
            "createdDate": "2017-12-18 12:25:01",
            "modifiedDate": "2025-04-23 23:28:31",
            "isOptional": false,
            "spaceVenueId": 1,
            "spaceId": 1,
            "spaceLayoutId": 0,
            "spaceCustomLayoutName": "C",
            "includeInPackage": true,
            "tariffId": 1,
            "roomHireType": 1,
            "minSpendAmount": 10,
            "minSpendRevenueItems": [
                1,
                2,
                3,
                4,
                5
            ],
            "overridePax": false,
            "costcenterId": 0,
            "amount": null,
            "excludedTaxIds": [],
            "sortOrder": 0,
            "sessionTypeId": 64,
            "sessionStatusId": 0,
            "beveragePackages": [
                {
                    "id": 1,
                    "name": "Morning tea",
                    "beverageVenueId": 1,
                    "beverageId": 1,
                    "numHours": null,
                    "startTime": "08:00:00",
                    "endTime": "09:00:00",
                    "sameAsSessionTime": true,
                    "itemsIds": [
                        1,
                        10
                    ],
                    "includeInPackage": false,
                    "costcenterId": 2,
                    "amount": 10,
                    "excludedTaxIds": [],
                    "createdDate": "2017-12-18 12:25:32",
                    "modifiedDate": "2025-04-23 05:52:34"
                },
                {
                    "id": 15,
                    "name": "Per Person - 30 Minute Pre-dinner Beverages",
                    "beverageVenueId": 1,
                    "beverageId": 7,
                    "numHours": null,
                    "startTime": "08:00:00",
                    "endTime": "09:00:00",
                    "sameAsSessionTime": true,
                    "itemsIds": [
                        11
                    ],
                    "includeInPackage": false,
                    "costcenterId": 2,
                    "amount": 15,
                    "excludedTaxIds": [
                        1
                    ],
                    "createdDate": "2025-04-23 05:53:02",
                    "modifiedDate": "2025-04-23 05:53:02"
                }
            ],
            "menus": [
                {
                    "id": 14,
                    "name": "Total of all items",
                    "menuVenueId": 1,
                    "menuId": 13,
                    "startTime": "08:00:00",
                    "endTime": "09:00:00",
                    "sameAsSessionTime": true,
                    "includeInPackage": false,
                    "costcenterId": 1,
                    "amount": 10,
                    "excludedTaxIds": [
                        317,
                        1955
                    ],
                    "createdDate": "2021-11-09 01:31:05",
                    "modifiedDate": "2025-04-23 05:28:22",
                    "items": [
                        {
                            "inventoryId": 8,
                            "groupId": "gr6189d144bfc41"
                        }
                    ],
                    "groups": [
                        {
                            "idHash": "gr6189d144bfc41",
                            "name": "Group 1",
                            "marketplaceName": "",
                            "minSelection": 1,
                            "maxSelection": 2,
                            "servingTime": null
                        }
                    ],
                    "costcenters": []
                },
                {
                    "id": 19,
                    "name": "Multi Cost center",
                    "menuVenueId": 1,
                    "menuId": 114,
                    "startTime": "08:00:00",
                    "endTime": "09:00:00",
                    "sameAsSessionTime": true,
                    "includeInPackage": false,
                    "costcenterId": 0,
                    "amount": 30,
                    "excludedTaxIds": [],
                    "createdDate": "2025-04-23 05:27:26",
                    "modifiedDate": "2025-04-23 05:27:26",
                    "items": [
                        {
                            "inventoryId": 10,
                            "groupId": ""
                        }
                    ],
                    "groups": [],
                    "costcenters": [
                        {
                            "id": 1,
                            "value": 10,
                            "excludedTaxIds": [
                                1046,
                                1955,
                                1986,
                                1988,
                                3910,
                                3979
                            ]
                        },
                        {
                            "id": 2,
                            "value": 20,
                            "excludedTaxIds": [
                                1,
                                317,
                                1046,
                                1955,
                                1986,
                                1988,
                                3910,
                                3979
                            ]
                        }
                    ]
                }
            ],
            "products": [
                {
                    "id": 3,
                    "productId": 13,
                    "includeInPackage": false,
                    "costcenterId": 3,
                    "amount": null,
                    "excludedTaxIds": [
                        317
                    ],
                    "createdDate": "2020-12-01 00:58:55",
                    "modifiedDate": "2025-04-23 06:17:48"
                }
            ],
            "resources": [
                {
                    "id": 16,
                    "resourceVenueId": 1,
                    "resourceId": 0,
                    "quantity": 1,
                    "includeInPackage": false,
                    "costcenterId": 1,
                    "amount": 0,
                    "excludedTaxIds": [],
                    "createdDate": "2022-04-05 04:49:30",
                    "modifiedDate": "2022-04-05 04:49:30"
                },
                {
                    "id": 22,
                    "resourceVenueId": 1,
                    "resourceId": 2,
                    "quantity": 1,
                    "includeInPackage": false,
                    "costcenterId": 2986,
                    "amount": 12,
                    "excludedTaxIds": [],
                    "createdDate": "2022-04-06 07:12:50",
                    "modifiedDate": "2022-04-06 07:12:50"
                },
                {
                    "id": 23,
                    "resourceVenueId": 1,
                    "resourceId": 3,
                    "quantity": 1,
                    "includeInPackage": false,
                    "costcenterId": 3,
                    "amount": 10,
                    "excludedTaxIds": [
                        1955,
                        1986,
                        3910,
                        3979
                    ],
                    "createdDate": "2022-04-13 23:31:13",
                    "modifiedDate": "2025-04-23 06:11:55"
                }
            ],
            "setupRequirements": [
                {
                    "id": 8,
                    "setupRequirementId": 1,
                    "name": "mysetuprequire",
                    "description": null,
                    "createdDate": "2025-04-23 06:38:29",
                    "modifiedDate": "2025-04-23 06:38:49",
                    "sortOrder": 2,
                    "hasChoices": false,
                    "minChoices": 1,
                    "maxChoices": 0,
                    "options": [
                        {
                            "id": 10,
                            "setupRequirementId": 1,
                            "setupRequirementOptionId": 2,
                            "name": "a",
                            "createdDate": "2025-04-23 06:38:29",
                            "modifiedDate": "2025-04-23 06:38:29",
                            "sortOrder": 0
                        },
                        {
                            "id": 11,
                            "setupRequirementId": 1,
                            "setupRequirementOptionId": 3,
                            "name": "b",
                            "createdDate": "2025-04-23 06:38:29",
                            "modifiedDate": "2025-04-23 06:38:29",
                            "sortOrder": 1
                        },
                        {
                            "id": 14,
                            "setupRequirementId": 1,
                            "setupRequirementOptionId": 8,
                            "name": "d",
                            "createdDate": "2025-04-23 23:29:27",
                            "modifiedDate": "2025-04-23 23:29:27",
                            "sortOrder": 3
                        }
                    ]
                },
                {
                    "id": 10,
                    "setupRequirementId": 18,
                    "name": "newsetup",
                    "description": null,
                    "createdDate": "2025-04-23 23:34:00",
                    "modifiedDate": "2025-04-23 23:34:00",
                    "sortOrder": 3,
                    "hasChoices": false,
                    "minChoices": 1,
                    "maxChoices": 0,
                    "options": [
                        {
                            "id": 15,
                            "setupRequirementId": 18,
                            "setupRequirementOptionId": 9,
                            "name": "newsetup1",
                            "createdDate": "2025-04-23 23:34:00",
                            "modifiedDate": "2025-04-23 23:34:00",
                            "sortOrder": 0
                        }
                    ]
                }
            ]
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`getVenuePackage`

```javascript
{
    "venueId": 1,
    "id": 1
}
```

## Package Details

| Property                     | Data Type   | Description                                                                                     |
|------------------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                           | integer     | The unique identifier of the package                                                          |
| name                         | string      | The name of the package                                                                       |
| type                         | enum [PackageType](get-venue-package-list.md#package-type)       | Simple or Detailed                       |
| minPax                       | integer     | The minimum pax of the package                                                               |
| maxPax                       | integer     | The maximum pax of the package                                                               |
| cost                         | float       | The price of the package (depends on the "priceMethod" value)                                 |
| priceMethod                  | enum [PriceMethod](get-venue-package-list.md#price-method)       | The type of package price - per person or flat rate |
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
| costcenters                  | array of [CostCenter](get-venue-package-list.md#cost-center)       | The cost centers to which the package applies. |
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
| sessions | array | The list sessions that is setup in the package. see [Session](get-venue-package.md#session-details) |

## Session Details

| Property               | Data Type   | Description                                                                                     |
|------------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                     | integer     | The unique identifier of the session                                                          |
| name                   | string      | The name of the session                                                                       |
| startTime              | time        | The start time of the session                                                                 |
| endTime                | time        | The end time of the session                                                                   |
| setupTime              | time        | The setup time of the session                                                                 |
| setdownTime            | time        | The setdown time of the session                                                               |
| createdDate            | datetime    | The date and time the session was created                                                    |
| modifiedDate           | datetime    | The date and time the session was last modified                                              |
| isOptional             | boolean     | Whether the session is optional                                                              |
| spaceVenueId           | integer     | The id of the venue to which the space belongs (it can be different to the booking venueId)   |
| spaceId                | integer     | The default space to be used for the session                                                 |
| spaceLayoutId          | integer     | The default layout to use for the selected space                                             |
| spaceCustomLayoutName  | string      | Layout Name for Custom space layout                                                          |
| includeInPackage       | boolean     | Whether the session is included in the package                                               |
| tariffId               | integer     | The tariff id of the session                                                                 |
| roomHireType           | integer     | The room hire type of the session                                                            |
| minSpendAmount         | float       | The minimum spend required for the room hire                                                 |
| minSpendRevenueItems   | array       | An array of revenue items that override the venue setup                                      |
| overridePax            | boolean     | Whether the number of attendees of this session can exceed the space's max pax               |
| costcenterId           | integer     | The cost center id of the session                                                            |
| amount                 | float       | The amount of the session (only used if includeInPackage is set to false)                    |
| excludedTaxIds         | array       | The tax component of the amount                                                              |
| sortOrder              | integer     | The sort order of the package sessions                                                       |
| sessionTypeId          | integer     | The id of the session type                                                                   |
| sessionStatusId        | integer     | The id of the session status                                                                 |
| beverages | array | Array of beverages in the session. See [Beverage](get-venue-package.md#beverage-package-details) |
| menus | array | Array of menus in the session. See [Menu](get-venue-package.md#menu-details) |
| products | array | Array of products in the session. See [Product](get-venue-package.md#product-details) |
| resources | array | Array of resources in the session. See [Resource](get-venue-package.md#resource-details)|
| setupRequirements | array | Array of setup requirements in the session. See [Setup Requirement](get-venue-package.md#setup-requirement-details) |

## Beverage Package Details

| Property            | Data Type   | Description                                                                                     |
|---------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                  | integer     | The unique identifier of the beverage                                                          |
| name                | string      | The name of the beverage                                                                       |
| beverageVenueId     | integer     | The id of the venue to which the beverage package belongs                                     |
| beverageId          | integer     | The id of the beverage package                                                               |
| numHours            | float       | The number of hours the beverage package is available                                        |
| startTime           | time        | The start time of the beverage                                                                |
| endTime             | time        | The end time of the beverage                                                                  |
| sameAsSessionTime   | boolean     | If this is true, then it copies start/end time based on session time                         |
| itemsIds            | array       | The items of the beverage                                                                     |
| includeInPackage    | boolean     | Whether the beverage is included in the package                                              |
| costcenterId        | integer     | The cost center id of the beverage                                                           |
| amount              | float       | The amount of the beverage (only used if includeInPackage is set to false)                   |
| excludedTaxIds      | array       | The tax component of the amount                                                             |
| createdDate         | datetime    | The date and time the beverage was created                                                   |
| modifiedDate        | datetime    | The date and time the beverage was last modified                                             |

## Menu Details

| Property            | Data Type   | Description                                                                                     |
|---------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                  | integer     | The unique identifier of the menu                                                          |
| name                | string      | The name of the menu                                                                       |
| menuVenueId         | integer     | The id of the venue to which the menu (menuId) belongs                                       |
| menuId              | integer     | The id of the menu                                                                           |
| startTime           | time        | The start time of the menu                                                                |
| endTime             | time        | The end time of the menu                                                                  |
| sameAsSessionTime   | boolean     | If this is true, then it copies start/end time based on session time                         |
| includeInPackage    | boolean     | Whether the menu is included in the package                                              |
| costcenterId        | integer     | The cost center id of the menu                                                           |
| amount              | float       | The amount of the menu (only used if includeInPackage is set to false)                   |
| excludedTaxIds      | array       | The tax component of the amount                                                             |
| createdDate         | datetime    | The date and time the menu was created                                                   |
| modifiedDate        | datetime    | The date and time the menu was last modified                                             |
| items               | array       | List of menu items. See [Menu Item](get-venue-package.md#menu-item)              |
| groups              | array       | List of menu groups. See [Menu Group](get-venue-package.md#menu-group)            |
| costcenters         | array       | List of Cost Centers value when menu is multi cost.See [Menu Cost Center](get-venue-package.md#menu-cost-center) |

### Menu Item

| Property    | Data Type   | Description                                                                                     |
|-------------|-------------|-------------------------------------------------------------------------------------------------|
| inventoryId | integer     | The inventory id of the item                                                                   |
| groupId     | string      | The group id to which item belongs. Empty when it belongs to no group                          |

### Menu Group

| Property         | Data Type   | Description                                                                                     |
|------------------|-------------|-------------------------------------------------------------------------------------------------|
| idHash           | string      | The hash id of the group                                                                      |
| name             | string      | The name of the group                                                                        |
| marketplaceName  | string      | The marketplace name of the group                                                           |
| minSelection     | integer     | The minimum selection of the group                                                          |
| maxSelection     | integer     | The maximum selection of the group                                                          |
| servingTime      | time        | The serving time of the group                                                               |

## Menu Cost Center

| Property         | Data Type   | Description                                      |
|------------------|-------------|--------------------------------------------------|
| id               | integer     | The cost center identifier                       |
| value            | float       | The amount of the cost center                    |
| excludedTaxIds   | array       | The tax ids excluded from the amount             |

## Product Details

| Property            | Data Type   | Description                                                                                     |
|---------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                  | integer     | The unique identifier of the product                                                          |
| productId           | integer     | The product id from inventory                                                                |
| includeInPackage    | boolean     | Whether the product is included in the package                                              |
| costcenterId        | integer     | The cost center id of the product                                                           |
| amount              | float       | The amount of the product (only used if includeInPackage is set to false)                   |
| excludedTaxIds      | array       | The tax component of the amount                                                             |
| createdDate         | datetime    | The date and time the product was created                                                   |
| modifiedDate        | datetime    | The date and time the product was last modified                                             |

## Resource Details

| Property            | Data Type   | Description                                                                                     |
|---------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                  | integer     | The unique identifier of the resource                                                          |
| resourceVenueId     | integer     | The venue id of the resource                                                                 |
| resourceId          | integer     | The resource id                                                                              |
| quantity            | integer     | The quantity of the resource                                                                |
| includeInPackage    | boolean     | Whether the resource is included in the package                                              |
| costcenterId        | integer     | The cost center id of the resource                                                           |
| amount              | float       | The amount of the resource (only used if includeInPackage is set to false)                   |
| excludedTaxIds      | array       | The tax component of the amount                                                             |
| createdDate         | datetime    | The date and time the resource was created                                                   |
| modifiedDate        | datetime    | The date and time the resource was last modified                                             |

## Setup Requirement Details

| Property            | Data Type   | Description                                                                                     |
|---------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                  | integer     | The unique identifier of the setup requirement                                                |
| setupRequirementId  | integer     | Related setup requirement id                                                                  |
| name                | string      | The name of the setup requirement                                                             |
| description         | string      | The description of the session                                                                |
| createdDate         | datetime    | The date and time the setup requirement was created                                           |
| modifiedDate        | datetime    | The date and time the setup requirement was last modified                                     |
| sortOrder           | integer     | The sort order of the session                                                                 |
| hasChoices          | boolean     | Whether the setup requirement has choices/options                                             |
| minChoices          | integer     | The minimum number of choices                                                                |
| maxChoices          | integer     | The maximum number of choices                                                                |
| options | array of [Setup Requirement Option](get-venue-package.md#setup-requirement-option-details)| The array of the setup requirement options when hasChoices is true   |

## Setup Requirement Option Details

| Property                   | Data Type   | Description                                                                                     |
|----------------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                         | integer     | The unique identifier of the setup requirement option                                         |
| setupRequirementId         | integer     | Related setup requirement id from inventory                                                   |
| setupRequirementOptionId   | integer     | Related setup requirement option id from inventory                                            |
| name                       | string      | The name of the setup requirement option                                                     |
| createdDate                | datetime    | The date and time the setup requirement option was created                                    |
| modifiedDate               | datetime    | The date and time the setup requirement option was last modified                              |
| sortOrder                  | integer     | The sort order of the setup requirement option                                               |


Note: The api will only return maximum of 100 items for each type session, menu, beverage product, etc.