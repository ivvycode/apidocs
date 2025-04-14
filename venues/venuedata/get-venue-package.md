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
    "id": 4,
    "name": "Test Package",
    "type": 1,
    "minPax": 0,
    "maxPax": 200,
    "cost": 3000,
    "priceMethod": 2,
    "actualCost": 20,
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
    "smallDescription": "Test",
    "largeDescription": "<p>test</p>\n",
    "marketplaceName": "Test Package",
    "isVisibleOnVenueSearch": true,
    "createdDate": "2015-03-05 05:36:33",
    "modifiedDate": "2025-03-28 03:10:49",
    "startDate": null,
    "endDate": null,
    "startTime": "09:00:00",
    "endTime": "11:00:00",
    "costcenters": [
        {
            "costcenterId": 1,
            "value": 500
        },
        {
            "costcenterId": 2,
            "value": 400
        },
        {
            "costcenterId": 3,
            "value": 300
        },
        {
            "costcenterId": 4,
            "value": 100
        },
        {
            "costcenterId": 5,
            "value": 500
        },
        {
            "costcenterId": 7,
            "value": 200
        },
        {
            "costcenterId": 32,
            "value": 300
        },
        {
            "costcenterId": 33,
            "value": 400
        },
        {
            "costcenterId": 966,
            "value": 300
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
    "spaceLayoutId": 2,
    "spaceCustomLayoutName": null,
    "sortOrder": 7,
    "excludedFromCommissions": false,
    "reduceRoomHireFirst": false,
    "eventTypes": [
        14,
        65
    ],
    "userGroupIds": [
        1,
        14
    ],
    "hasLimitedStartTimes": true,
    "limitedStartTimes": [
        "01:30:00",
        "02:00:00",
        "03:30:00"
    ],
    "isAccommIncluded": false,
    "discountCampaignId": 2,
    "costcentersDiscounts": [
        {
            "costcenterId": 4,
            "value": 10
        },
        {
            "costcenterId": 5,
            "value": 10
        },
        {
            "costcenterId": 7,
            "value": 10
        },
        {
            "costcenterId": 2,
            "value": 10
        },
        {
            "costcenterId": 3,
            "value": 10
        },
        {
            "costcenterId": 6,
            "value": 10
        },
        {
            "costcenterId": 966,
            "value": 10
        },
        {
            "costcenterId": 8389,
            "value": 10
        },
        {
            "costcenterId": 8390,
            "value": 10
        },
        {
            "costcenterId": 1,
            "value": 10
        }
    ],
    "sessions": [
        {
            "id": 123,
            "name": "First Session",
            "startTime": "09:00:00",
            "endTime": "11:00:00",
            "setupTime": 10,
            "setdownTime": 10,
            "createdDate": "2017-02-01 23:33:24",
            "modifiedDate": "2025-03-28 03:16:49",
            "isOptional": false,
            "spaceVenueId": 1,
            "spaceId": 2,
            "spaceLayoutId": 1,
            "spaceCustomLayoutName": null,
            "includeInPackage": false,
            "tariffId": 1,
            "roomHireType": 5,
            "minSpendAmount": 100,
            "minSpendRevenueItems": [
                1,
                2
            ],
            "overridePax": true,
            "costcenterId": 5,
            "amount": 255,
            "excludedTaxIds": [],
            "sortOrder": 0,
            "sessionTypeId": 1,
            "sessionStatusId": 12,
            "beverages": [
                {
                    "id": 25,
                    "name": null,
                    "packageId": 4,
                    "sessionId": 123,
                    "beverageVenueId": 0,
                    "beverageId": 0,
                    "numHours": null,
                    "startTime": null,
                    "endTime": null,
                    "sameAsSessionTime": false,
                    "items": null,
                    "includeInPackage": false,
                    "costcenterId": 966,
                    "amount": 10,
                    "excludedTaxIds": [],
                    "createdDate": "2025-03-28 03:20:21",
                    "modifiedDate": "2025-03-28 03:20:21"
                }
            ],
            "menus": [
                {
                    "id": 80,
                    "name": "Test Menu",
                    "packageId": 4,
                    "sessionId": 123,
                    "menuVenueId": 1,
                    "menuId": 2815,
                    "startTime": "09:00:00",
                    "endTime": "11:00:00",
                    "sameAsSessionTime": true,
                    "includeInPackage": false,
                    "costcenterId": 0,
                    "amount": 50,
                    "excludedTaxIds": [],
                    "createdDate": "2025-03-28 03:17:43",
                    "modifiedDate": "2025-03-28 03:17:43",
                    "items": [
                        {
                            "inventoryId": 221,
                            "groupId": "gr61383783cb967"
                        },
                        {
                            "inventoryId": 222,
                            "groupId": "gr61383783cb967"
                        },
                        {
                            "inventoryId": 223,
                            "groupId": "gr613837910adac"
                        },
                        {
                            "inventoryId": 224,
                            "groupId": "gr613837910adac"
                        }
                    ],
                    "groups": [
                        {
                            "idHash": "gr61383783cb967",
                            "name": "Menu Group 1",
                            "marketplaceName": "",
                            "minSelection": 0,
                            "maxSelection": 0,
                            "servingTime": ""
                        },
                        {
                            "idHash": "gr613837910adac",
                            "name": "Menu Group 2",
                            "marketplaceName": "",
                            "minSelection": 0,
                            "maxSelection": 0,
                            "servingTime": ""
                        }
                    ],
                    "costcenters": [
                        {
                            "costcenterId": 2,
                            "amount": 20,
                            "excludedTaxIds": [
                                1,
                                6064,
                                6146,
                                6221
                            ]
                        },
                        {
                            "costcenterId": 3,
                            "amount": 30,
                            "excludedTaxIds": [
                                1,
                                6064,
                                6146,
                                6221
                            ]
                        }
                    ]
                }
            ],
            "products": [
                {
                    "id": 25,
                    "packageId": 4,
                    "sessionId": 123,
                    "productId": 2,
                    "includeInPackage": false,
                    "costcenterId": 966,
                    "amount": 10,
                    "excludedTaxIds": [],
                    "createdDate": "2025-03-28 03:20:21",
                    "modifiedDate": "2025-03-28 03:20:21"
                }
            ],
            "resources": [
                {
                    "id": 441,
                    "packageId": 4,
                    "sessionId": 123,
                    "resourceVenueId": 1,
                    "resourceId": 2672,
                    "quantity": 10,
                    "includeInPackage": false,
                    "costcenterId": 4,
                    "amount": 50,
                    "excludedTaxIds": [],
                    "createdDate": "2025-03-28 03:20:09",
                    "modifiedDate": "2025-03-28 03:20:09"
                }
            ],
            "setupRequirements": [
                {
                    "id": 165,
                    "packageId": 4,
                    "sessionId": 123,
                    "setupRequirementId": 3,
                    "name": "Mic with Options",
                    "description": "<p>Global Mic</p>\n",
                    "createdDate": "2025-03-28 03:20:55",
                    "modifiedDate": "2025-03-28 03:20:55",
                    "sortOrder": 0,
                    "hasChoices": 0,
                    "minChoices": 0,
                    "maxChoices": 0,
                    "options": [
                        {
                            "id": 22,
                            "packageId": 4,
                            "sessionId": 123,
                            "packageSessionSetupId": 165,
                            "setupRequirementId": 3,
                            "setupRequirementOptionId": 7,
                            "name": "Mic Option 1",
                            "createdDate": "2025-03-28 03:20:55",
                            "modifiedDate": "2025-03-28 03:20:55",
                            "sortOrder": 0
                        },
                        {
                            "id": 23,
                            "packageId": 4,
                            "sessionId": 123,
                            "packageSessionSetupId": 165,
                            "setupRequirementId": 3,
                            "setupRequirementOptionId": 8,
                            "name": "Mic Option 2",
                            "createdDate": "2025-03-28 03:20:55",
                            "modifiedDate": "2025-03-28 03:20:55",
                            "sortOrder": 1
                        }
                    ]
                },
                {
                    "id": 166,
                    "packageId": 4,
                    "sessionId": 123,
                    "setupRequirementId": 7,
                    "name": "Table Fans",
                    "description": null,
                    "createdDate": "2025-03-28 03:20:55",
                    "modifiedDate": "2025-03-28 03:20:55",
                    "sortOrder": 1,
                    "hasChoices": 0,
                    "minChoices": 0,
                    "maxChoices": 0,
                    "options": []
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
| costcenters                  | array       | The cost centers to which the package applies.                                                |
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
| items               | array       | The items of the beverage                                                                     |
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
| costcenterId     | integer     | The cost center identifier                      |
| amount           | float       | The amount of the cost center                  |
| excludedTaxIds   | array       | The tax ids excluded from the amount  |

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
| options | array| The array of the setup requirement options when hasChoices is true   |

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