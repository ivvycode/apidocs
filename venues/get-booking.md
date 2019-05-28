---
description: >-
  Note: Section sessions, packages, additionalItems, beveragePackages, menus,
  resources, products and serviceFees are not published yet.
---

# Get Booking

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getBooking" path="" %}
{% api-method-summary %}
Get Booking
{% endapi-method-summary %}

{% api-method-description %}
Get the details of a specific booking to which the user has access.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The id of the booking
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "id": 3,
  "venueId": 1,
  "code": "123a",
  "name": "Ava Donovan",
  "eventType": "Holiday",
  "companyId": null,
  "company": null,
  "contactId": null,
  "contact": null,
  "isConfidential": false,
  "currentStatus": 3,
  "totalAmount": 2600,
  "totalTaxAmount": 0,
  "amountOutstanding": 2600,
  "accountTimezone": "Australia/Brisbane",
  "venueTimezone": "Australia/Brisbane",
  "createdDate": "2015-01-21 09:50:49 UTC",
  "modifiedDate": "2016-04-06 07:51:56 UTC",
  "dateEventStart": "1996-02-19 00:00:00 UTC",
  "dateEventEnd": "2002-11-06 00:00:00 UTC",
  "isAccommIncluded": false,
  "dateAccomStart": "",
  "dateAccomEnd": "",
  "focRoomsDenominator": 0,
  "maxNumFocRoomsPerDay: 0,
  "hasPackages": true,
  "decisionDate": "",
  "canBeMoved": false,
  "bookedById": 123,
  "isBeoFinalised": false,
  "beoFinalisedDate": "",
  "dailyRevenue": [
    {
      "costcenterId": 1276,
      "revenueDate": "2015-09-04",
      "totalAmount": 2500,
      "totalTaxAmount": 227.273
    },
    {
      "costcenterId": 1277,
      "revenueDate": "2015-09-04",
      "totalAmount": 2500,
      "totalTaxAmount": 227.273
    },
    {
      "costcenterId": 1278,
      "revenueDate": "2015-09-04",
      "totalAmount": 2500,
      "totalTaxAmount": 227.273
    },
    {
      "costcenterId": 1279,
      "revenueDate": "2015-09-04",
      "totalAmount": 2500,
      "totalTaxAmount": 227.273
    }
  ],
  "packages": [
    {
      "id": 5082,
      "bookingDate": "2018-12-30",
      "numberAttendees": 30,
      "price": 40,
      "createdDate": "2018-11-07 03:56:35 UTC",
      "modifiedDate": "2018-11-07 03:56:35 UTC",
      "totalAmount": 1200,
      "totalTaxAmount": 109.091,
      "priceMethod": 1,
      "costcenters": [
        {
          "costcenterId": 2,
          "value": 10,
          "excludedTaxIds": [],
          "totalAmount": 300,
          "totalTaxAmount": 27.272727,
          "taxDetails": [
            {
              "id": 1,
              "tax": 27.272727
            }
          ]
        },
        {
          "costcenterId": 3,
          "value": 10,
          "excludedTaxIds": [],
          "totalAmount": 300,
          "totalTaxAmount": 27.272727,
          "taxDetails": [
            {
              "id": 1,
              "tax": 27.272727
            }
          ]
        },
        {
          "costcenterId": 4,
          "value": 10,
          "excludedTaxIds": [],
          "totalAmount": 300,
          "totalTaxAmount": 27.272727,
          "taxDetails": [
            {
              "id": 1,
              "tax": 27.272727
            }
          ]
        },
        {
          "costcenterId": 5,
          "value": 10,
          "excludedTaxIds": [],
          "totalAmount": 300,
          "totalTaxAmount": 27.272727,
          "taxDetails": [
            {
              "id": 1,
              "tax": 27.272727
            }
          ]
        }
      ],
      "taxDetails": [
        {
          "id": 1,
          "tax": 109.091
        }
      ],
      "smallDescription": "Package Small Description"
    }
  ],
  "sessions": [
    {
      "id": 13185,
      "name": "Computer Graphics",
      "startDate": "2018-12-30",
      "endDate": "2018-12-30",
      "startTime": "10:00:00",
      "endTime": "11:00:00",
      "spaceVenueId": 1,
      "spaceId": 2,
      "spaceLayout": null,
      "customLayoutName": "Custom",
      "cost": 50,
      "totalAmount": 50,
      "totalTaxAmount": 4.545,
      "excludedTaxIds": [],
      "costcenterId": 5,
      "includeInPackage": false,
      "bookingPackageId": 5082,
      "createdDate": "2018-11-07 03:56:35 UTC",
      "modifiedDate": "2018-11-07 03:57:36 UTC",
      "taxDetails": [
        {
          "id": 1,
          "tax": 4.545
        }
      ]
    }
  ],
  "menus": [
    {
      "id": 6686,
      "name": "Main Course",
      "menuVenueId": 1,
      "menuId": 3,
      "sessionId": 13185,
      "cost": 10,
      "excludedTaxIds": [],
      "startDate": "2018-12-30",
      "endDate": "2018-12-30",
      "startTime": "10:00:00",
      "endTime": "11:00:00",
      "includeInPackage": false,
      "bookingPackageId": null,
      "createdDate": "2018-11-15 06:48:38 UTC",
      "modifiedDate": "2018-11-15 06:48:38 UTC",
      "costcenterId": 2,
      "totalAmount": 300,
      "totalTaxAmount": 27.273,
      "taxDetails": [
        {
          "id": 1,
          "tax": 27.273
        }
      ]
    }
  ],
  "beveragePackages": [
    {
      "id": 6204,
      "name": "Beverage Package 1",
      "sessionId": 13185,
      "beverageVenueId": 1,
      "beverageId": 2,
      "cost": 70,
      "excludedTaxIds": [],
      "startDate": "2018-12-30",
      "endDate": "2018-12-30",
      "startTime": "10:00:00",
      "endTime": "11:00:00",
      "includeInPackage": false,
      "bookingPackageId": null,
      "createdDate": "2018-11-15 06:48:58 UTC",
      "modifiedDate": "2018-11-15 06:48:58 UTC",
      "costcenterId": 3,
      "totalAmount": 2100,
      "totalTaxAmount": 190.909,
      "taxDetails": [
        {
          "id": 1,
          "tax": 190.909
        }
      ]
    }
  ],
  "resources": [
    {
      "id": 6437,
      "name": null,
      "sessionId": 13185,
      "cost": 5,
      "excludedTaxIds": [],
      "quantity": 1,
      "startDate": "2018-12-30",
      "endDate": "2018-12-30",
      "startTime": "10:00:00",
      "endTime": "11:00:00",
      "includeInPackage": false,
      "bookingPackageId": null,
      "createdDate": "2018-11-15 06:49:31 UTC",
      "modifiedDate": "2018-11-15 06:49:31 UTC",
      "costcenterId": 4,
      "totalAmount": 5,
      "totalTaxAmount": 0.455,
      "taxDetails": [
        {
          "id": 1,
          "tax": 0.455
        }
      ]
    }
  ],
  "products": [
    {
      "id": 5305,
      "name": null,
      "sessionId": 13185,
      "cost": 100,
      "excludedTaxIds": [],
      "quantity": 1,
      "includeInPackage": false,
      "bookingPackageId": null,
      "createdDate": "2018-11-15 06:49:57 UTC",
      "modifiedDate": "2018-11-15 06:49:57 UTC",
      "costcenterId": 4,
      "totalAmount": 100,
      "totalTaxAmount": 9.091,
      "taxDetails": [
        {
          "id": 1,
          "tax": 9.091
        }
      ]
    }
  ],
  "additionalItems": [
    {
      "id": 3935,
      "description": "Some Additional Item",
      "quantity": 1,
      "totalCost": 100,
      "totalCostExcludedTaxIds": [
        3676
      ],
      "actualCost": 0,
      "actualCostExcludedTaxIds": [],
      "createdDate": "2018-11-15 07:18:17 UTC",
      "modifiedDate": "2018-11-16 01:15:05 UTC",
      "costcenterId": 4,
      "totalAmount": 100,
      "totalTaxAmount": 9.091,
      "startDateTime": null,
      "endDateTime": null,
      "taxDetails": [
        {
          "id": 1,
          "tax": 9.091
        }
      ],
      "dayTaxDetails": []
    },
    {
      "id": 3936,
      "description": "Another additional item",
      "quantity": 1,
      "totalCost": 110,
      "totalCostExcludedTaxIds": [],
      "actualCost": 0,
      "actualCostExcludedTaxIds": [],
      "createdDate": "2018-11-15 07:19:59 UTC",
      "modifiedDate": "2018-11-15 07:19:59 UTC",
      "costcenterId": 4,
      "totalAmount": 110,
      "totalTaxAmount": 10,
      "startDateTime": "2018-12-30 09:00:00",
      "endDateTime": "2019-01-01 10:00:00",
      "taxDetails": [
        {
          "id": 1,
          "tax": 9.999
        }
      ],
      "dayTaxDetails": [
        {
          "date": "2018-12-30",
          "taxDetails": [
            {
              "id": 1,
              "tax": 3.333333
            }
          ]
        },
        {
          "date": "2018-12-31",
          "taxDetails": [
            {
              "id": 1,
              "tax": 3.333333
            }
          ]
        },
        {
          "date": "2019-01-01",
          "taxDetails": [
            {
              "id": 1,
              "tax": 3.333333
            }
          ]
        }
      ]
    }
  ],
  "serviceFees": [
    {
      "id": 3262,
      "refType": 9,
      "refId": 3936,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 4,
      "amount": 3.333333,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:36 UTC",
      "modifiedDate": "2018-11-20 00:15:09 UTC",
      "totalAmount": 3.666333,
      "totalTaxAmount": 0.333,
      "taxDetails": [
        {
          "id": 1,
          "tax": 0.333
        }
      ]
    },
    {
      "id": 3264,
      "refType": 9,
      "refId": 3936,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-31",
      "refCostcenterId": 4,
      "amount": 3.333333,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:36 UTC",
      "modifiedDate": "2018-11-20 00:15:09 UTC",
      "totalAmount": 3.666333,
      "totalTaxAmount": 0.333,
      "taxDetails": [
        {
          "id": 1,
          "tax": 0.333
        }
      ]
    },
    {
      "id": 3266,
      "refType": 9,
      "refId": 3936,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2019-01-01",
      "refCostcenterId": 4,
      "amount": 3.333333,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:36 UTC",
      "modifiedDate": "2018-11-20 00:15:09 UTC",
      "totalAmount": 3.666333,
      "totalTaxAmount": 0.333,
      "taxDetails": [
        {
          "id": 1,
          "tax": 0.333
        }
      ]
    },
    {
      "id": 3271,
      "refType": 3,
      "refId": 5082,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 2,
      "amount": 27.272727,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:36 UTC",
      "modifiedDate": "2018-11-20 00:15:09 UTC",
      "totalAmount": 29.999727,
      "totalTaxAmount": 2.727,
      "taxDetails": [
        {
          "id": 1,
          "tax": 2.727
        }
      ]
    },
    {
      "id": 3272,
      "refType": 3,
      "refId": 5082,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 3,
      "amount": 27.272727,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:36 UTC",
      "modifiedDate": "2018-11-20 00:15:09 UTC",
      "totalAmount": 29.999727,
      "totalTaxAmount": 2.727,
      "taxDetails": [
        {
          "id": 1,
          "tax": 2.727
        }
      ]
    },
    {
      "id": 3273,
      "refType": 3,
      "refId": 5082,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 4,
      "amount": 27.272727,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:36 UTC",
      "modifiedDate": "2018-11-20 00:15:09 UTC",
      "totalAmount": 29.999727,
      "totalTaxAmount": 2.727,
      "taxDetails": [
        {
          "id": 1,
          "tax": 2.727
        }
      ]
    },
    {
      "id": 3274,
      "refType": 3,
      "refId": 5082,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 5,
      "amount": 27.272727,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:37 UTC",
      "modifiedDate": "2018-11-20 00:15:09 UTC",
      "totalAmount": 29.999727,
      "totalTaxAmount": 2.727,
      "taxDetails": [
        {
          "id": 1,
          "tax": 2.727
        }
      ]
    },
    {
      "id": 3275,
      "refType": 4,
      "refId": 13185,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 5,
      "amount": 4.546,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:37 UTC",
      "modifiedDate": "2018-11-20 00:15:10 UTC",
      "totalAmount": 5.001,
      "totalTaxAmount": 0.455,
      "taxDetails": [
        {
          "id": 1,
          "tax": 0.455
        }
      ]
    },
    {
      "id": 3276,
      "refType": 5,
      "refId": 6686,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 2,
      "amount": 27.273,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:37 UTC",
      "modifiedDate": "2018-11-20 00:15:10 UTC",
      "totalAmount": 30,
      "totalTaxAmount": 2.727,
      "taxDetails": [
        {
          "id": 1,
          "tax": 2.727
        }
      ]
    },
    {
      "id": 3277,
      "refType": 6,
      "refId": 6204,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 3,
      "amount": 190.909,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:37 UTC",
      "modifiedDate": "2018-11-20 00:15:10 UTC",
      "totalAmount": 210,
      "totalTaxAmount": 19.091,
      "taxDetails": [
        {
          "id": 1,
          "tax": 19.091
        }
      ]
    },
    {
      "id": 3278,
      "refType": 7,
      "refId": 5305,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 4,
      "amount": 9.091,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:37 UTC",
      "modifiedDate": "2018-11-20 00:15:10 UTC",
      "totalAmount": 10,
      "totalTaxAmount": 0.909,
      "taxDetails": [
        {
          "id": 1,
          "tax": 0.909
        }
      ]
    },
    {
      "id": 3279,
      "refType": 8,
      "refId": 6437,
      "ref2Id": 0,
      "ref3Id": 0,
      "refDate": "2018-12-30",
      "refCostcenterId": 4,
      "amount": 0.455,
      "excludedTaxIds": [],
      "createdDate": "2018-11-15 07:27:37 UTC",
      "modifiedDate": "2018-11-20 00:15:10 UTC",
      "totalAmount": 0.501,
      "totalTaxAmount": 0.046,
      "taxDetails": [
        {
          "id": 1,
          "tax": 0.046
        }
      ]
    },
    "salesPersonUser": {
        "id": 1,
        "firstName": "Jack",
        "lastName": "Smith",
        "email": "jack@smith.com",
        "phone": 61482154689
    },
    "bookedByUser": {
        "id": 3,
        "firstName": "Oliver",
        "lastName": "Brown",
        "email": "oliver@brown.com",
        "phone": 61582154689
    },
    "leadBccEmail": "lead-1-111-6895d8@ivvy.com",
    "foodBeveragePayableBy": 1,
    "totalAttendees": 20,
    "hasCommissions": 1,
    "hasCommissionPaid": 1,
    "agent": {
        "id": 2,
        "businessName": "company Name",
        "email": "company@name.com",
        "phone": "+354-80-6090113"
    },
    "commissionByCostCentres": [{
        "2019-04-04": {
            "costcenterId": 2,
            "commission": 31.7
        },
        "2019-04-05": {
            "costcenterId": 2,
            "commission": 1.7
        }
    }],
    "bookingType": 1
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be the details of a specific booking to which the user has access. The unique booking identifier is required, for example {“id”:123}

## Example Request

```text
{
    "id":3
}
```

## Booking

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the booking |
| venueId | integer | The venue identifier of the booking |
| code | string | A reference assigned to the booking by the venue \(not unique\) |
| name | string | The name of the booking |
| eventType | string | The event type of the booking |
| companyId | integer | The unique id of the company assigned to the booking |
| company | [Company](get-booking.md#company) | The details of the company assigned to the booking |
| contactId | integer | The unique id of the contact assigned to the booking |
| contact | [Contact](get-booking.md#contact) | The details of the contact assigned to the booking |
| isConfidential | boolean | Whether or not the booking is confidential |
| currentStatus | enum | The current status of the booking. See [Status](get-booking.md#status) |
| totalAmount | double | The total amount of the booking, including tax |
| totalTaxAmount | double | The total tax of the booking |
| amountOutstanding | double | The amount outstanding of the booking, including tax |
| accountTimezone | [timezone](../development-reference/timezone-list.md) | The timezone of the account |
| venueTimezone | [timezone](../development-reference/timezone-list.md) | The timezone of the venue |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date & time the booking was created |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date & time the booking was last modified |
| dateEventStart | [timestamp](../development-reference/timestamp-format.md) | The start event date of the booking |
| dateEventEnd | [timestamp](../development-reference/timestamp-format.md) | The end event date of the booking |
| isAccommIncluded | boolean | Whether or not the booking includes accommodation |
| dateAccomStart | [timestamp](../development-reference/timestamp-format.md) | The start accommodation date of the booking |
| dateAccomEnd | [timestamp](../development-reference/timestamp-format.md) | The end accommodation date of the booking |
| focRoomsDenominator | int | The number of accommodation rooms in which one room is complimentary. For example if the value is 5, then 1 in 5 accommodation rooms will be complimentary. |
| maxNumFocRoomsPerDay | int | The maximum number of accommodation rooms per day that can be complimentary |
| hasPackages | boolean | Whether or not the booking has packages |
| decisionDate | [timestamp](../development-reference/timestamp-format.md) | The date before which the event/accommodation dates must be decided |
| canBeMoved | boolean | Whether or not the event/accommodation dates of the booking are flexible |
| bookedById | integer | The unique id of the event coordinator user assigned to the booking |
| isBeoFinalised | boolean | Whether or not the BEO of the booking has been finalised |
| beoFinalisedDate | [timestamp](../development-reference/timestamp-format.md) | The date & time on which the BEO of the booking was finalised |
| dailyRevenue | Array of [DailyRevenue](get-booking.md#daily-revenue) | The daily revenue data of booking |
| packages | Array of [Package](get-booking.md#package) | The list of packages of the booking |
| sessions | Array of [Session](get-booking.md#session) | The list of sessions of booking |
| menus | Array of [Menu](get-booking.md#menu) | The list of menus of the booking |
| beveragePackages | Array of [Beverage Package](get-booking.md#beverage-package) | The list of beverage packages of the booking |
| resources | Array of [Resource](get-booking.md#menu) | The list of resources of the booking |
| products | Array of [Product](get-booking.md#product) | The list of products of the booking |
| additionalItems | Array of [Additional Item](get-booking.md#additional-item) | The list of additional items of the booking |
| serviceFees | Array of [Service Fees](get-booking.md#service-fee) | The list of service fee applied to different items of the booking |
| salesPersonUser | Array of [Sales Person](get-booking.md#sales-person) | The details of sales Person in the booking |
| bookedByUser | Array of [Booked By](get-booking.md#booked-by) | The details of the user that created the booking |
| leadBccEmail | string | The email address that can be used to record emails against this lead |
| foodBeveragePayableBy | enum \([Food Beverage Payable By](get-booking.md#food-beverage-payableby)\) | The Food and Beverage can be payable by |
| totalAttendees | integer | The total number of attendees for the booking |
| hasCommissions | boolean | The booking pay comissions to an agent |
| hasCommissionPaid | boolean | The commission has been paid for the booking |
| agent | Array of [Agent](get-booking.md#agent) | The details of the agent in the booking |
| commissionByCostCentres | Array of [Commission By Cost Centres](get-booking.md#commission-by-cost-centres) | The commission amount by Cost Centres in the Booking |
| bookingType | enum \([Booking Types](get-booking.md#get-booking.md#booking-types)\) | The type of Booking selected for the Booking |

## Status

One of the following values:

| \# | Description |
| :--- | :--- |
| 1 | Prospective |
| 2 | Tentative |
| 3 | Confirmed |
| 4 | Cancelled |
| 5 | Ordering |
| 8 | Not Accepted |

## Daily Revenue

| Property | Type | Description |
| :--- | :--- | :--- |
| costcenterId | integer | The unique identifier of the cost center to which the revenue applies |
| revenueDate | [Date](../development-reference/date-format.md) | The date on which the revenue applies |
| totalAmount | double | The total revenue amount, including tax |
| totalTaxAmount | double | The total tax amount that is included in the total revenue amount |

## Company

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the company |
| businessName | integer | The business name of the company |

## Contact

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the contact |
| firstName | string | The first name of the contact |
| lastName | string | The last name of the contact |
| email | string | The email address of the contact |
| phone | string | The phone number of the contact |

## Package

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier for the booking package |
| bookingDate | [Date](../development-reference/date-format.md) | The date of the package |
| numberAttendees | integer | The number of attendees for the booking package |
| price | double | The price of the booking package |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date and time when the booking package was added to this booking |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date and time when the booking package was last modified |
| totalAmount | double | The total amount of the booking package including tax amount |
| totalTaxAmount | double | The tax amount of the booking package |
| priceMethod | enum \([Package Price Method](get-booking.md#package-price-method)\) | The price method of the booking package |
| costcenters | Array of [Package Cost Centre](get-booking.md#package-cost-center) | The list of costcenter and its individual value of the booking package |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details |
| smallDescription | string | The small description of the booking package |

## Package Price Method

| Value | Description |
| :--- | :--- |
| 1 | Per Person |
| 2 | Flat Rate |

## Package Cost Center

| Property | Type | Description |
| :--- | :--- | :--- |
| costcenterId | integer | The unique identifier of the cost center |
| value | double | The amount of the cost center |
| excludedTaxIds | array | The excluded tax identifiers |
| totalAmount | double | The amount of the cost center |
| totalTaxAmount | double | The total tax amount of the cost center |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | The individual tax amount |

## Session

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the session |
| name | string | The name of the session |
| startDate | [Date](../development-reference/date-format.md) | The start date of the session |
| endDate | [Date](../development-reference/date-format.md) | The end date of the session |
| startTime | Time | The start time of the session |
| endTime | Time | The end time of the session |
| spaceVenueId | integer | The id of the venue to which the space \(spaceId\) belongs \(it can be different to the booking's venueId\) |
| spaceId | integer | The space identifier booked by the session |
| spaceLayout | integer | The space layout identifier of the session |
| customLayoutName | string | The space layout name when space layout is custom |
| cost | double | The cost of the session |
| totalAmount | double | The total amount of session including tax amount |
| totalTaxAmount | double | The tax amount of the session |
| excludedTaxIds | array | The excluded tax identifiers of the session |
| costcenterId | integer | The cost center identifier to which the session's revenue applies |
| includeInPackage | boolean | Whether or not the booking session is included in booking package |
| bookingPackageId | integer | The booking package identifier if the booking session is included in package |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date and time when the session was created |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date and time when the session was last modified |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details |

## Menu

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the menu |
| name | string | The name of the menu |
| menuVenueId | integer | The venue identifier to which the menu package belongs. This can be different than booking's venue id |
| menuId | integer | The reference menu identifier in venue menus |
| sessionId | integer | The session identifier to which this menu belongs |
| cost | double | The cost of the menu |
| excludedTaxIds | array | The excluded tax identifiers |
| startDate | [Date](../development-reference/date-format.md) | The start date of the menu |
| endDate | [Date](../development-reference/date-format.md) | The end date of the menu |
| startTime | Time | The start time of the menu |
| endTime | Time | The end time of the menu |
| includeInPackage | boolean | Whether or not the menu is included in booking package |
| bookingPackageId | integer | The booking package identifier if menu is included in package |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the menu was created |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the menu was last modified |
| costcenterId | integer | The cost center identifier to which the revenue applies |
| totalAmount | double | The total amount of the menu including tax |
| totalTaxAmount | double | The tax amount of the menu |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details |

## Beverage Package

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the beverage package |
| name | string | The name of the beverage package |
| sessionId | integer | The session identifier to which this beverage package belongs |
| beverageVenueId | integer | The venue identifier to which the beverage package belongs. This can be different than booking's venue id |
| beverageId | integer | The reference beverage package identifier in venue beverage packages |
| cost | double | The cost of the beverage package |
| excludedTaxIds | array | The excluded tax identifiers |
| startDate | [Date](../development-reference/date-format.md) | The start date of the beverage package |
| endDate | [Date](../development-reference/date-format.md) | The end date of the beverage package |
| startTime | Time | The start time of the beverage package |
| endTime | Time | The end time of the beverage package |
| includeInPackage | boolean | Whether or not the beverage package is included in booking package |
| bookingPackageId | integer | The booking package identifier if beverage package is included in package |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the beverage package was created |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the beverage package was last modified |
| costcenterId | integer | The cost center identifier to which the revenue applies |
| totalAmount | double | The total amount of the beverage package including tax |
| totalTaxAmount | double | The tax amount of the beverage package |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details |

## Resource

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the resource |
| name | string | The name of the resource |
| sessionId | integer | The session identifier to which this resource belongs |
| cost | double | The cost of the resource |
| excludedTaxIds | array | The excluded tax identifiers |
| quantity | integer | The quantity of the resource |
| startDate | [Date](../development-reference/date-format.md) | The start date of the resource |
| endDate | [Date](../development-reference/date-format.md) | The end date of the resource |
| startTime | Time | The start time of the resource |
| endTime | Time | The end time of the resource |
| includeInPackage | boolean | Whether or not the resource is included in booking package |
| bookingPackageId | integer | The booking package identifier if resource is included in package |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the resource was created |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the resource was last modified |
| costcenterId | integer | The cost center identifier to which the revenue applies |
| totalAmount | double | The total amount of the resource including tax |
| totalTaxAmount | double | The tax amount of the resource |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details |

## Product

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the product |
| name | string | The name of the product |
| sessionId | integer | The session identifier to which this product belongs |
| cost | double | The cost of the product |
| excludedTaxIds | array | The excluded tax identifiers |
| quantity | integer | The quantity of the product |
| includeInPackage | boolean | Whether or not the product is included in booking package |
| bookingPackageId | integer | The booking package identifier if product is included in package |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the product was created |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the product was last modified |
| costcenterId | integer | The cost center identifier to which the revenue applies |
| totalAmount | double | The total amount of the product including tax |
| totalTaxAmount | double | The tax amount of the product |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details |

## Additional Item

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The list of additional items of the booking |
| description | string | The description of the item |
| quantity | double | The quantity of the item |
| totalCost | double | The sale price of the item |
| totalCostExcludedTaxIds | array | The sale price excluded tax identifiers |
| actualCost | double | The cost of the item |
| actualCostExcludedTaxIds | array | The cost excluded tax identifiers |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date and time when the item was created |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date and time when the item was last modified |
| costcenterId | integer | The cost center identifier to which the revenue applies |
| totalAmount | double | The total amount of the item including tax amount |
| totalTaxAmount | double | The tax amount of the item |
| startDateTime | [timestamp](../development-reference/timestamp-format.md) | The start date and time of the item |
| endDateTime | [timestamp](../development-reference/timestamp-format.md) | The end date and time of item |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details |
| dayTaxDetails | Array of [Day Tax Detail](get-booking.md#day-tax-detail) | The individual tax for each date. Empty when start date time is empty. |

## Service Fee

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the applied service fee |
| refType | enum \([Service Fee Reference Type](get-booking.md#service-fee-reference-types)\) | The item reference type to which the service fee applies |
| refId | integer | The first identifier for identifying reference item in the booking |
| ref2Id | integer | The second identifier for identifying the reference item in the booking |
| ref3Id | integer | The third identifier for identifying the reference item in the booking |
| refDate | [Date](../development-reference/date-format.md) | The date on which the fee applies |
| refCostcenterId | integer | The reference cost centre identifier to which the fee applies |
| amount | double | The amount of the service fee without tax |
| excludedTaxIds | array | The list of excluded tax ids |
| createdDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the product was created |
| modifiedDate | [timestamp](../development-reference/timestamp-format.md) | The date and time the product was last modified |
| totalAmount | double | The total amount of the service including tax |
| totalTaxAmount | double | The tax amount of the service fee |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details |

## Tax Detail

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of tax in venue |
| tax | double | The amount of tax applied |

## Day Tax Detail

| Property | Type | Description |
| :--- | :--- | :--- |
| date | [Date](../development-reference/date-format.md) | The day to which taxes applies |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail) | Individual tax details for the day |

## Service Fee Reference Types

| Value | Description | Value of refId | Value of ref2Id | Value of ref3Id |
| :--- | :--- | :--- | :--- | :--- |
| 1 | Booking Accommodation | Booking Accommodation Identifier |  |  |
| 2 | Booking Accommodation Option | Booking Accommodation Identifier | Booking Accommodation Option Id \(roomOptionId\) | Booking Accommodation Option Number \(roomOptionNum\) |
| 3 | Package | Booking Package Identifier |  |  |
| 4 | Session | Booking Session Identifier |  |  |
| 5 | Menu / Food | Booking Session Menu Identifier |  |  |
| 6 | Beverage Package | Booking Session Beverage Package Identifier |  |  |
| 7 | Product | Booking Session Product Identifier |  |  |
| 8 | Resource | Booking Session Resource Identifier |  |  |
| 9 | Additional Item | Booking Additional Item Identifier |  |  |
| 11 | Service | Booking Service Identifier |  |  |

## Commission By Cost Centres

| Property | Type | Description |
| :--- | :--- | :--- |
| costcenterId | integer | The cost center identifier to which the revenue applies |
| commission | integer | The commission amount by Cost Centres in the Booking |

## Booking Types

One of the following values:

| \# | Description |
| :--- | :--- |
| 1 | Simple |
| 2 | Detailed |
| 3 | Accommodation Only |

## Food Beverage Payable By

One of the following values:

| \# | Description |
| :--- | :--- |
| 1 | Master Account |
| 2 | Guests |

## Sales Person

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the sales person |
| firstName | string | The first name of the sales person |
| lastName | string | The last name of the sales person |
| email | string | The email address of the sales person |
| phone | string | The phone number of the sales person |

## Booked By

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the co-ordinator |
| firstName | string | The first name of the co-ordinator |
| lastName | string | The last name of the co-ordinator |
| email | string | The email address of the co-ordinator |
| phone | string | The phone number of the co-ordinator |

## Agent

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique identifier of the company |
| businessName | integer | The business name of the company |
| email | string | The email address of the company |
| phone | string | The phone number of the company |

