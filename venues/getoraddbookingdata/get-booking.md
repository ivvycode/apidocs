---
description: >-
  Note: Section sessions, packages, additionalItems, beveragePackages, menus,
  resources, products and serviceFees are not published yet.
---

# Get Booking

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getBooking" method="post" summary="Get Booking" %}
{% swagger-description %}
Get the details of a specific booking to which the user has access.
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The id of the booking
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "id": 3,
  "venueId": 1,
  "code": "123a",
  "name": "Ava Donovan",
  "eventType": "Holiday",
  "eventTypeId": 2,
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
  "lastModifiedDate": "2016-04-09 07:50:51 UTC",
  "dateEventStart": "1996-02-19 00:00:00 UTC",
  "dateEventEnd": "2002-11-06 00:00:00 UTC",
  "convertedToTentative": "2016-02-23 00:00:00 UTC",
  "convertedToConfirmed": "2016-03-05 12:49:31 UTC",
  "convertedToCancelled": "2016-02-28 00:00:00 UTC",
  "isAccommIncluded": false,
  "dateAccomStart": "",
  "dateAccomEnd": "",
  "focRoomsDenominator": 0,
  "maxNumFocRoomsPerDay: 0,
  "hasPackages": true,
  "decisionDate": "",
  "canBeMoved": false,
  "bookedById": 123,
  "beoNumbers": ["18-1", "19-1", "20-1"],
  "isBeoFinalised": false,
  "beoFinalisedDate": "",
  "otaFolioRef": "ven1234",
  "accommReservationMethod": [
        1,
        2,
        3
  ],
  "accommCutOffDate": "2019-12-04 00:00:00 UTC",
  "accommCancellationDate": "2019-01-11 00:00:00 UTC",
  "accommChargingMethod": 2,
  "accommGuaranteeRequired": false,
  "accommExternalBlockId": "test 123",
  "dailyRevenue": [
    {
      "venueId": 1,
      "costcenterId": 1276,
      "revenueDate": "2015-09-04",
      "totalAmount": 900,
      "totalDiscountAmount": 100,
      "totalTaxAmount": 81.818
    },
    {
      "venueId": 1,
      "costcenterId": 1277,
      "revenueDate": "2015-09-04",
      "totalAmount": 900,
      "totalDiscountAmount": 100,
      "totalTaxAmount": 81.818
    },
    {
      "venueId": 1,
      "costcenterId": 1278,
      "revenueDate": "2015-09-04",
      "totalAmount": 900,
      "totalDiscountAmount": 100,
      "totalTaxAmount": 81.818
    },
    {
      "venueId": 1,
      "costcenterId": 1279,
      "revenueDate": "2015-09-04",
      "totalAmount": 900,
      "totalDiscountAmount": 100,
      "totalTaxAmount": 81.818
    },
    ...
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
      "totalDiscount": 100,
      "totalTaxAmount": 109.091,
      "priceMethod": 1,
      "costcenters": [
        {
          "costcenterId": 2,
          "value": 10,
          "excludedTaxIds": [],
          "totalAmount": 300,
          "totalDiscount": 100,
          "totalTaxAmount": 27.272727,
          "taxDetails": [
            {
              "id": 1,
              "tax": 27.272727,
              "rateId": 0,
              "rateAmount": 0,
              "rateAmountType": 0
            }
          ]
        },
        {
          "costcenterId": 3,
          "value": 10,
          "excludedTaxIds": [],
          "totalAmount": 300,
          "totalDiscount": 100,
          "totalTaxAmount": 27.272727,
          "taxDetails": [
            {
              "id": 1,
              "tax": 27.272727,
              "rateId": 0,
              "rateAmount": 0,
              "rateAmountType": 0
            }
          ]
        },
        {
          "costcenterId": 4,
          "value": 10,
          "excludedTaxIds": [],
          "totalAmount": 300,
          "totalDiscount": 100,
          "totalTaxAmount": 27.272727,
          "taxDetails": [
            {
              "id": 1,
              "tax": 27.272727,
              "rateId": 0,
              "rateAmount": 0,
              "rateAmountType": 0
            }
          ]
        },
        {
          "costcenterId": 5,
          "value": 10,
          "excludedTaxIds": [],
          "totalAmount": 300,
          "totalDiscount": 100,
          "totalTaxAmount": 27.272727,
          "taxDetails": [
            {
              "id": 1,
              "tax": 27.272727,
              "rateId": 0,
              "rateAmount": 0,
              "rateAmountType": 0
            }
          ]
        }
      ],
      "taxDetails": [
        {
          "id": 1,
          "tax": 109.091,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
      "tariffId": 50,
      "cost": 50,
      "discount": 5,
      "totalAmount": 50,
      "totalDiscount": 10,
      "totalTaxAmount": 4.545,
      "excludedTaxIds": [],
      "costcenterId": 5,
      "includeInPackage": false,
      "bookingPackageId": 5082,
      "beoNumbers": ["19-1"],
      "createdDate": "2018-11-07 03:56:35 UTC",
      "modifiedDate": "2018-11-07 03:57:36 UTC",
      "taxDetails": [
        {
          "id": 1,
          "tax": 4.545,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
        }
      ],
      "totalAttendees": 2000,
    }
  ],
  "menus": [
    {
      "id": 6686,
      "name": "Main Course",
      "menuVenueId": 1,
      "menuId": 3,
      "menuCategoryId": 3,
      "sessionId": 13185,
      "cost": 10,
      "discount": 5,
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
      "totalDiscount": 10,
      "totalTaxAmount": 27.273,
      "taxDetails": [
        {
          "id": 1,
          "tax": 27.273,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
        }
      ],
      "totalAttendees": 2000,
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
      "discount": 5,
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
      "totalDiscount": 10,
      "totalTaxAmount": 190.909,
      "taxDetails": [
        {
          "id": 1,
          "tax": 190.909,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
        }
      ],
      "totalAttendees": 2000,
    }
  ],
  "resources": [
    {
      "id": 6437,
      "name": null,
      "sessionId": 13185,
      "cost": 5,
      "discount": 5,
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
      "totalDiscount": 10,
      "totalTaxAmount": 0.455,
      "taxDetails": [
        {
          "id": 1,
          "tax": 0.455,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0          ,
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
      "discount": 5,
      "excludedTaxIds": [],
      "quantity": 1,
      "includeInPackage": false,
      "bookingPackageId": null,
      "createdDate": "2018-11-15 06:49:57 UTC",
      "modifiedDate": "2018-11-15 06:49:57 UTC",
      "costcenterId": 4,
      "totalAmount": 100,
      "totalDiscount": 10,
      "totalTaxAmount": 9.091,
      "taxDetails": [
        {
          "id": 1,
          "tax": 9.091,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
      "totalCostDiscount": 10,
      "totalCostExcludedTaxIds": [
        3676
      ],
      "actualCost": 0,
      "actualCostExcludedTaxIds": [],
      "createdDate": "2018-11-15 07:18:17 UTC",
      "modifiedDate": "2018-11-16 01:15:05 UTC",
      "costcenterId": 4,
      "totalAmount": 100,
      "totalDiscount": 10,
      "totalTaxAmount": 9.091,
      "startDateTime": null,
      "endDateTime": null,
      "taxDetails": [
        {
          "id": 1,
          "tax": 9.091,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
        }
      ],
      "dayTaxDetails": []
    },
    {
      "id": 3936,
      "description": "Another additional item",
      "quantity": 1,
      "totalCost": 110,
      "totalCostDiscount": 11,
      "totalCostExcludedTaxIds": [],
      "actualCost": 0,
      "actualCostExcludedTaxIds": [],
      "createdDate": "2018-11-15 07:19:59 UTC",
      "modifiedDate": "2018-11-15 07:19:59 UTC",
      "costcenterId": 4,
      "totalAmount": 110,
      "totalDiscount": 10,
      "totalTaxAmount": 10,
      "startDateTime": "2018-12-30 09:00:00",
      "endDateTime": "2019-01-01 10:00:00",
      "taxDetails": [
        {
          "id": 1,
          "tax": 9.999,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
        }
      ],
      "dayTaxDetails": [
        {
          "date": "2018-12-30",
          "taxDetails": [
            {
              "id": 1,
              "tax": 3.333333,
              "rateId": 0,
              "rateAmount": 0,
              "rateAmountType": 0
            }
          ]
        },
        {
          "date": "2018-12-31",
          "taxDetails": [
            {
              "id": 1,
              "tax": 3.333333,
              "rateId": 0,
              "rateAmount": 0,
              "rateAmountType": 0
            }
          ]
        },
        {
          "date": "2019-01-01",
          "taxDetails": [
            {
              "id": 1,
              "tax": 3.333333,
              "rateId": 0,
              "rateAmount": 0,
              "rateAmountType": 0
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
          "tax": 0.333,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 0.333,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 0.333,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 2.727,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 2.727,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 2.727,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 2.727,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 0.455,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 2.727,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 19.091,
          "rateId": 0,
          "rateAmount": 0,
          "rateAmountType": 0
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
          "tax": 0.909,
          "rateId": 2,
          "rateAmount": 6,
          "rateAmountType": 2
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
          "tax": 0.046,
          "rateId": 1,
          "rateAmount": 5,
          "rateAmountType": 1
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
    "commissionByCostCentres": [
      {
        "costcenterId": 2,
        "commission": 31.7
      },
      {
        "costcenterId": 2,
        "commission": 1.7
      }
    ],
    "bookingType": 1,
    "opportunityId": 2,
  ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be the details of a specific booking to which the user has access. The unique booking identifier is required, for example {“id”:123}

## Example Request

```
{
    "id":3
}
```

## Booking

| Property                | Type                                                                             | Description                                                                                                                                                 |
| ----------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                      | integer                                                                          | The unique identifier of the booking                                                                                                                        |
| venueId                 | integer                                                                          | The venue identifier of the booking                                                                                                                         |
| code                    | string                                                                           | A reference assigned to the booking by the venue (only unique within a single venue)                                                                        |
| name                    | string                                                                           | The name of the booking                                                                                                                                     |
| eventType               | string                                                                           | The event type of the booking                                                                                                                               |
| eventTypeId             | integer                                                                          | The event type id of the booking                                                                                                                            |
| companyId               | integer                                                                          | The unique id of the company assigned to the booking                                                                                                        |
| company                 | [Company](get-booking.md#company)                                                | The details of the company assigned to the booking                                                                                                          |
| contactId               | integer                                                                          | The unique id of the contact assigned to the booking                                                                                                        |
| contact                 | [Contact](get-booking.md#contact)                                                | The details of the contact assigned to the booking                                                                                                          |
| isConfidential          | boolean                                                                          | Whether or not the booking is confidential                                                                                                                  |
| currentStatus           | enum                                                                             | The current status of the booking. See [Status](get-booking.md#status)                                                                                      |
| totalAmount             | double                                                                           | The total amount of the booking, including tax                                                                                                              |
| totalTaxAmount          | double                                                                           | The total tax of the booking                                                                                                                                |
| amountOutstanding       | double                                                                           | The amount outstanding of the booking, including tax                                                                                                        |
| accountTimezone         | [timezone](../../development-reference/timezone-list.md)                         | The timezone of the account                                                                                                                                 |
| venueTimezone           | [timezone](../../development-reference/timezone-list.md)                         | The timezone of the venue                                                                                                                                   |
| createdDate             | [timestamp](../../development-reference/timestamp-format.md)                     | The date & time the booking was created                                                                                                                     |
| modifiedDate            | [timestamp](../../development-reference/timestamp-format.md)                     | The date & time the booking was last modified                                                                                                               |
| lastModifiedDate        | [timestamp](../../development-reference/timestamp-format.md)                     | The last modified date & time the booking or its children like Accommodation, Package, Session, Additional Items, etc.                                      |
| dateEventStart          | [timestamp](../../development-reference/timestamp-format.md)                     | The start event date of the booking                                                                                                                         |
| dateEventEnd            | [timestamp](../../development-reference/timestamp-format.md)                     | The end event date of the booking                                                                                                                           |
| convertedToTentative    | [timestamp](../../development-reference/timestamp-format.md)                     | The date when booking converted to tentatvive                                                                                                               |
| convertedToConfirmed    | [timestamp](../../development-reference/timestamp-format.md)                     | The date when booking converted to confirmed                                                                                                                |
| convertedToCancelled    | [timestamp](../../development-reference/timestamp-format.md)                     | The date when booking converted to cancelled                                                                                                                |
| isAccommIncluded        | boolean                                                                          | Whether or not the booking includes accommodation                                                                                                           |
| dateAccomStart          | [timestamp](../../development-reference/timestamp-format.md)                     | The start accommodation date of the booking                                                                                                                 |
| dateAccomEnd            | [timestamp](../../development-reference/timestamp-format.md)                     | The end accommodation date of the booking                                                                                                                   |
| focRoomsDenominator     | int                                                                              | The number of accommodation rooms in which one room is complimentary. For example if the value is 5, then 1 in 5 accommodation rooms will be complimentary. |
| maxNumFocRoomsPerDay    | int                                                                              | The maximum number of accommodation rooms per day that can be complimentary                                                                                 |
| hasPackages             | boolean                                                                          | Whether or not the booking has packages                                                                                                                     |
| decisionDate            | [timestamp](../../development-reference/timestamp-format.md)                     | The date before which the event/accommodation dates must be decided                                                                                         |
| canBeMoved              | boolean                                                                          | Whether or not the event/accommodation dates of the booking are flexible                                                                                    |
| bookedById              | integer                                                                          | The unique id of the event coordinator user assigned to the booking                                                                                         |
| beoNumbers              | array                                                                            | The id/numbers for the BEO documents assigned to the booking                                                                                                |
| isBeoFinalised          | boolean                                                                          | Whether or not the BEO of the booking has been finalised                                                                                                    |
| beoFinalisedDate        | [timestamp](../../development-reference/timestamp-format.md)                     | The date & time on which the BEO of the booking was finalised                                                                                               |
| accommReservationMethod | [Reservation Method](add-or-update-booking.md#accommodation-reservation-methods) | optional | The method by which attendees will reserve rooms from the accommodation blocks on the booking. Only applies when the booking includes accommodation. |
| otaFolioRef             | string                                                                           | The recorded Folio ID of a booking.                                                                                                                         |
| accommCutOffDate        | [timestamp](../../development-reference/timestamp-format.md)                     | After this date no more reservations may be made against the Block for the entire date range.                                                               |
| accommCancellationDate  | [timestamp](../../development-reference/timestamp-format.md)                     | The last date a customer can cancel their Group Accommodation without financial penalty.                                                                    |
| accommChargingMethod    | enum ([Charging Method](get-booking.md#get-booking.md#charging-method))          | A record of the Charging Method for Documents, Note that values will still need to be altered in the Block.                                                 |
| accommGuaranteeRequired | boolean                                                                          | Indicates whether the customer is required to guarantee their reservation with a credit card.                                                               |
| accommExternalBlockId   | string                                                                           | The Block ID from an external PMS.                                                                                                                          |
| dailyRevenue            | Array of [DailyRevenue](get-booking.md#daily-revenue)                            | The daily revenue data of booking                                                                                                                           |
| packages                | Array of [Package](get-booking.md#package)                                       | The list of packages of the booking                                                                                                                         |
| sessions                | Array of [Session](get-booking.md#session)                                       | The list of sessions of booking                                                                                                                             |
| menus                   | Array of [Menu](get-booking.md#menu)                                             | The list of menus of the booking                                                                                                                            |
| beveragePackages        | Array of [Beverage Package](get-booking.md#beverage-package)                     | The list of beverage packages of the booking                                                                                                                |
| resources               | Array of [Resource](get-booking.md#menu)                                         | The list of resources of the booking                                                                                                                        |
| products                | Array of [Product](get-booking.md#product)                                       | The list of products of the booking                                                                                                                         |
| additionalItems         | Array of [Additional Item](get-booking.md#additional-item)                       | The list of additional items of the booking                                                                                                                 |
| serviceFees             | Array of [Service Fees](get-booking.md#service-fee)                              | The list of service fee applied to different items of the booking                                                                                           |
| salesPersonUser         | Array of [Sales Person](get-booking.md#sales-person)                             | The details of sales Person in the booking                                                                                                                  |
| bookedByUser            | Array of [Booked By](get-booking.md#booked-by)                                   | The details of the user that created the booking                                                                                                            |
| leadBccEmail            | string                                                                           | The email address that can be used to record emails against this lead                                                                                       |
| foodBeveragePayableBy   | enum ([Food Beverage Payable By](get-booking.md#food-beverage-payableby))        | The Food and Beverage can be payable by                                                                                                                     |
| totalAttendees          | integer                                                                          | The total number of attendees for the booking                                                                                                               |
| hasCommissions          | boolean                                                                          | The booking pay comissions to an agent                                                                                                                      |
| hasCommissionPaid       | boolean                                                                          | The commission has been paid for the booking                                                                                                                |
| agent                   | Array of [Agent](get-booking.md#agent)                                           | The details of the agent in the booking                                                                                                                     |
| commissionByCostCentres | Array of [Commission By Cost Centres](get-booking.md#commission-by-cost-centres) | The commission amount by Cost Centres in the Booking                                                                                                        |
| bookingType             | enum ([Booking Types](get-booking.md#get-booking.md#booking-types))              | The type of Booking selected for the Booking                                                                                                                |
| opportunityId           | integer                                                                          | The id of the Opportunity for the Booking                                                                                                                   |
| hasCateringWebsite | boolean | Whether or not the catering website is enabled for the booking |
| cateringWebsiteLogoId | string | The catering website logo for the booking |
| cateringWebsiteLogo | [File](get-booking.md#file) | The catering website logo for the booking |
| cateringWebsiteBannerId | string | The catering website banner for the booking |
| cateringWebsiteBanner | [File](get-booking.md#file) | The catering website banner for the booking |
| cateringWebsiteEventDesc | string | The catering website event description for the booking |
| cateringWebsiteEndNumDays | integer | The catering website end num days from event start for the booking |


## File

| Property            | Type | Description |
| ------------------- | ---- | ----------- |
| id | integer  | The file identifier |
| accountId | integer  | The account id of a file |
| originalFileName | string  | The original file name |
| size | integer  | Size of the file |
| tags | array  | Tags related to the file |
| contentType | string  | Content type of the file |
| url | string  | Url of the file |


## Status

One of the following values:

| # | Description      |
| - | ---------------- |
| 1 | Prospective      |
| 2 | Tentative        |
| 3 | Confirmed        |
| 4 | Cancelled        |
| 5 | Ordering         |
| 8 | Not Accepted     |
| 9 | Prospective Hold |

## Daily Revenue

| Property            | Type                                               | Description                                                           |
| ------------------- | -------------------------------------------------- | --------------------------------------------------------------------- |
| venueId             | integer                                            | The unique identifier of the venue to which the cost center belongs   |
| costcenterId        | integer                                            | The unique identifier of the cost center to which the revenue applies |
| revenueDate         | [Date](../../development-reference/date-format.md) | The date on which the revenue applies                                 |
| totalAmount         | double                                             | The total revenue amount, including tax                               |
| totalDiscountAmount | number                                             | The amount of total discount                                          |
| totalTaxAmount      | double                                             | The total tax amount that is included in the total revenue amount     |

## Company

| Property     | Type    | Description                          |
| ------------ | ------- | ------------------------------------ |
| id           | integer | The unique identifier of the company |
| businessName | integer | The business name of the company     |

## Contact

| Property  | Type    | Description                          |
| --------- | ------- | ------------------------------------ |
| id        | integer | The unique identifier of the contact |
| firstName | string  | The first name of the contact        |
| lastName  | string  | The last name of the contact         |
| email     | string  | The email address of the contact     |
| phone     | string  | The phone number of the contact      |

## Package

| Property         | Type                                                               | Description                                                            |
| ---------------- | ------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| id               | integer                                                            | The unique identifier for the booking package                          |
| bookingDate      | [Date](../../development-reference/date-format.md)                 | The date of the package                                                |
| numberAttendees  | integer                                                            | The number of attendees for the booking package                        |
| price            | double                                                             | The price of the booking package                                       |
| createdDate      | [timestamp](../../development-reference/timestamp-format.md)       | The date and time when the booking package was added to this booking   |
| modifiedDate     | [timestamp](../../development-reference/timestamp-format.md)       | The date and time when the booking package was last modified           |
| totalAmount      | double                                                             | The total amount of the booking package including tax amount           |
| totalDiscount    | double                                                             | The total amount of the discount                                       |
| totalSurcharge   | double                                                             | The total amount of the surcharge                                      |
| totalTaxAmount   | double                                                             | The tax amount of the booking package                                  |
| priceMethod      | enum ([Package Price Method](get-booking.md#package-price-method)) | The price method of the booking package                                |
| costcenters      | Array of [Package Cost Centre](get-booking.md#package-cost-center) | The list of costcenter and its individual value of the booking package |
| taxDetails       | Array of [Tax Detail](get-booking.md#tax-detail)                   | Individual tax details                                                 |
| smallDescription | string                                                             | The small description of the booking package                           |
| packageId        | string                                                             | The id of the venue package                                            |
| packageName      | string                                                             | The name of the venue package                                          |

## Package Price Method

| Value | Description |
| ----- | ----------- |
| 1     | Per Person  |
| 2     | Flat Rate   |

## Package Cost Center

| Property       | Type                                             | Description                              |
| -------------- | ------------------------------------------------ | ---------------------------------------- |
| costcenterId   | integer                                          | The unique identifier of the cost center |
| value          | double                                           | The amount of the cost center            |
| discount       | double                                           | The amount of the discount on value      |
| surcharge      | double                                           | The amount of the surcharge on value     |
| excludedTaxIds | array                                            | The excluded tax identifiers             |
| totalAmount    | double                                           | The amount of the cost center            |
| totalSurcharge | double                                           | The amount of the total surcharge        |
| totalTaxAmount | double                                           | The total tax amount of the cost center  |
| taxDetails     | Array of [Tax Detail](get-booking.md#tax-detail) | The individual tax amount                |

## Session

| Property         | Type                                                         | Description                                                                                             |
| ---------------- | ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| id               | integer                                                      | The unique identifier of the session                                                                    |
| name             | string                                                       | The name of the session                                                                                 |
| startDate        | [Date](../../development-reference/date-format.md)           | The start date of the session                                                                           |
| endDate          | [Date](../../development-reference/date-format.md)           | The end date of the session                                                                             |
| startTime        | [Time](../../development-reference/time-format.md)           | The start time of the session                                                                           |
| endTime          | [Time](../../development-reference/time-format.md)           | The end time of the session                                                                             |
| spaceVenueId     | integer                                                      | The id of the venue to which the space (spaceId) belongs (it can be different to the booking's venueId) |
| spaceId          | integer                                                      | The space identifier booked by the session                                                              |
| spaceLayout      | integer                                                      | The space layout identifier of the session                                                              |
| customLayoutName | string                                                       | The space layout name when space layout is custom                                                       |
| cost             | double                                                       | The cost of the session                                                                                 |
| discount         | double                                                       | The amount of the discount on cost                                                                      |
| totalAmount      | double                                                       | The total amount of session including tax amount                                                        |
| totalDiscount    | double                                                       | The total amount of the discount                                                                        |
| totalSurcharge   | double                                                       | The total amount of the surcharge                                                                       |
| totalTaxAmount   | double                                                       | The tax amount of the session                                                                           |
| excludedTaxIds   | array                                                        | The excluded tax identifiers of the session                                                             |
| costcenterId     | integer                                                      | The cost center identifier to which the session's revenue applies                                       |
| includeInPackage | boolean                                                      | Whether or not the booking session is included in booking package                                       |
| bookingPackageId | integer                                                      | The booking package identifier if the booking session is included in package                            |
| beoNumbers       | array                                                        | The id/numbers of the BEO documents assigned to the booking session                                     |
| createdDate      | [timestamp](../../development-reference/timestamp-format.md) | The date and time when the session was created                                                          |
| modifiedDate     | [timestamp](../../development-reference/timestamp-format.md) | The date and time when the session was last modified                                                    |
| taxDetails       | Array of [Tax Detail](get-booking.md#tax-detail)             | Individual tax details                                                                                  |
| totalAttendees   | integer                                                      | The minimum number of attendees for the Booking session                                                 |

## Menu

| Property         | Type                                                         | Description                                                                                           |
| ---------------- | ------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------- |
| id               | integer                                                      | The unique identifier of the menu                                                                     |
| name             | string                                                       | The name of the menu                                                                                  |
| menuVenueId      | integer                                                      | The venue identifier to which the menu package belongs. This can be different than booking's venue id |
| menuId           | integer                                                      | The reference menu identifier in venue menus                                                          |
| menuTypeCategory | integer ([Menu Category List](get-booking.md#menu-category)) | The reference menu category identifier in venue menus                                                 |
| sessionId        | integer                                                      | The session identifier to which this menu belongs                                                     |
| cost             | double                                                       | The cost of the menu                                                                                  |
| discount         | double                                                       | The amount of the discount on cost                                                                    |
| surcharge        | double                                                       | The amount of the surcharge on cost                                                                   |
| excludedTaxIds   | array                                                        | The excluded tax identifiers                                                                          |
| startDate        | [Date](../../development-reference/date-format.md)           | The start date of the menu                                                                            |
| endDate          | [Date](../../development-reference/date-format.md)           | The end date of the menu                                                                              |
| startTime        | [Time](../../development-reference/time-format.md)           | The start time of the menu                                                                            |
| endTime          | [Time](../../development-reference/time-format.md)           | The end time of the menu                                                                              |
| includeInPackage | boolean                                                      | Whether or not the menu is included in booking package                                                |
| bookingPackageId | integer                                                      | The booking package identifier if menu is included in package                                         |
| createdDate      | [timestamp](../../development-reference/timestamp-format.md) | The date and time the menu was created                                                                |
| modifiedDate     | [timestamp](../../development-reference/timestamp-format.md) | The date and time the menu was last modified                                                          |
| costcenterId     | integer                                                      | The cost center identifier to which the revenue applies                                               |
| totalAmount      | double                                                       | The total amount of the menu including tax                                                            |
| totalDiscount    | double                                                       | The total amount of the discount                                                                      |
| totalSurcharge   | double                                                       | The total amount of the surcharge                                                                     |
| totalTaxAmount   | double                                                       | The tax amount of the menu                                                                            |
| taxDetails       | Array of [Tax Detail](get-booking.md#tax-detail)             | Individual tax details                                                                                |
| totalAttendees   | integer                                                      | The minimum number of attendees for the menu                                                          |
| costcenters | array of [Costcenter](get-booking.md#costcenter) | optional | Cost breakdown of a menu when selected menu type is multi cost per person|

## Beverage Package

| Property         | Type                                                         | Description                                                                                               |
| ---------------- | ------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| id               | integer                                                      | The unique identifier of the beverage package                                                             |
| name             | string                                                       | The name of the beverage package                                                                          |
| sessionId        | integer                                                      | The session identifier to which this beverage package belongs                                             |
| beverageVenueId  | integer                                                      | The venue identifier to which the beverage package belongs. This can be different than booking's venue id |
| beverageId       | integer                                                      | The reference beverage package identifier in venue beverage packages                                      |
| cost             | double                                                       | The cost of the beverage package                                                                          |
| discount         | double                                                       | The amount of the discount on cost                                                                        |
| surcharge        | double                                                       | The amount of the surcharge on cost                                                                       |
| excludedTaxIds   | array                                                        | The excluded tax identifiers                                                                              |
| startDate        | [Date](../../development-reference/date-format.md)           | The start date of the beverage package                                                                    |
| endDate          | [Date](../../development-reference/date-format.md)           | The end date of the beverage package                                                                      |
| startTime        | [Time](../../development-reference/time-format.md)           | The start time of the beverage package                                                                    |
| endTime          | [Time](../../development-reference/time-format.md)           | The end time of the beverage package                                                                      |
| includeInPackage | boolean                                                      | Whether or not the beverage package is included in booking package                                        |
| bookingPackageId | integer                                                      | The booking package identifier if beverage package is included in package                                 |
| createdDate      | [timestamp](../../development-reference/timestamp-format.md) | The date and time the beverage package was created                                                        |
| modifiedDate     | [timestamp](../../development-reference/timestamp-format.md) | The date and time the beverage package was last modified                                                  |
| costcenterId     | integer                                                      | The cost center identifier to which the revenue applies                                                   |
| totalAmount      | double                                                       | The total amount of the beverage package including tax                                                    |
| totalDiscount    | double                                                       | The total amount of the discount                                                                          |
| totalSurcharge   | double                                                       | The total amount of the surcharge                                                                         |
| totalTaxAmount   | double                                                       | The tax amount of the beverage package                                                                    |
| taxDetails       | Array of [Tax Detail](get-booking.md#tax-detail)             | Individual tax details                                                                                    |
| totalAttendees   | integer                                                      | The minimum number of attendees for the beverage package                                                  |
| smallDescription | double                                                       | The small description of the beverage package                                                             |
| marketplaceName  | double                                                       | The marketplace name of the beverage package                                                              |

## Resource

| Property         | Type                                                         | Description                                                       |
| ---------------- | ------------------------------------------------------------ | ----------------------------------------------------------------- |
| id               | integer                                                      | The unique identifier of the resource                             |
| name             | string                                                       | The name of the resource                                          |
| sessionId        | integer                                                      | The session identifier to which this resource belongs             |
| cost             | double                                                       | The cost of the resource                                          |
| discount         | double                                                       | The amount of the discount on cost                                |
| surcharge        | double                                                       | The amount of the surcharge on cost                               |
| excludedTaxIds   | array                                                        | The excluded tax identifiers                                      |
| quantity         | integer                                                      | The quantity of the resource                                      |
| startDate        | [Date](../../development-reference/date-format.md)           | The start date of the resource                                    |
| endDate          | [Date](../../development-reference/date-format.md)           | The end date of the resource                                      |
| startTime        | [Time](../../development-reference/time-format.md)           | The start time of the resource                                    |
| endTime          | [Time](../../development-reference/time-format.md)           | The end time of the resource                                      |
| includeInPackage | boolean                                                      | Whether or not the resource is included in booking package        |
| bookingPackageId | integer                                                      | The booking package identifier if resource is included in package |
| createdDate      | [timestamp](../../development-reference/timestamp-format.md) | The date and time the resource was created                        |
| modifiedDate     | [timestamp](../../development-reference/timestamp-format.md) | The date and time the resource was last modified                  |
| costcenterId     | integer                                                      | The cost center identifier to which the revenue applies           |
| totalAmount      | double                                                       | The total amount of the resource including tax                    |
| totalDiscount    | double                                                       | The total amount of the discount                                  |
| totalSurcharge   | double                                                       | The total amount of the surcharge                                 |
| totalTaxAmount   | double                                                       | The tax amount of the resource                                    |
| taxDetails       | Array of [Tax Detail](get-booking.md#tax-detail)             | Individual tax details                                            |

## Product

| Property         | Type                                                         | Description                                                      |
| ---------------- | ------------------------------------------------------------ | ---------------------------------------------------------------- |
| id               | integer                                                      | The unique identifier of the product                             |
| name             | string                                                       | The name of the product                                          |
| sessionId        | integer                                                      | The session identifier to which this product belongs             |
| cost             | double                                                       | The cost of the product                                          |
| discount         | double                                                       | The amount of the discount on cost                               |
| surcharge        | double                                                       | The amount of the surcharge on cost                              |
| excludedTaxIds   | array                                                        | The excluded tax identifiers                                     |
| quantity         | integer                                                      | The quantity of the product                                      |
| includeInPackage | boolean                                                      | Whether or not the product is included in booking package        |
| bookingPackageId | integer                                                      | The booking package identifier if product is included in package |
| createdDate      | [timestamp](../../development-reference/timestamp-format.md) | The date and time the product was created                        |
| modifiedDate     | [timestamp](../../development-reference/timestamp-format.md) | The date and time the product was last modified                  |
| costcenterId     | integer                                                      | The cost center identifier to which the revenue applies          |
| totalAmount      | double                                                       | The total amount of the product including tax                    |
| totalDiscount    | double                                                       | The total amount of the discount                                 |
| totalSurcharge   | double                                                       | The total amount of the surcharge                                |
| totalTaxAmount   | double                                                       | The tax amount of the product                                    |
| taxDetails       | Array of [Tax Detail](get-booking.md#tax-detail)             | Individual tax details                                           |

## Additional Item

| Property                 | Type                                                         | Description                                                            |
| ------------------------ | ------------------------------------------------------------ | ---------------------------------------------------------------------- |
| id                       | integer                                                      | The list of additional items of the booking                            |
| description              | string                                                       | The description of the item                                            |
| quantity                 | double                                                       | The quantity of the item                                               |
| totalCost                | double                                                       | The sale price of the item                                             |
| totalCostDiscount        | double                                                       | The amount of the discount on totalCost                                |
| totalCostSurcharge       | double                                                       | The amount of the surcharge on totalCost                               |
| totalCostExcludedTaxIds  | array                                                        | The sale price excluded tax identifiers                                |
| actualCost               | double                                                       | The cost of the item                                                   |
| actualCostExcludedTaxIds | array                                                        | The cost excluded tax identifiers                                      |
| createdDate              | [timestamp](../../development-reference/timestamp-format.md) | The date and time when the item was created                            |
| modifiedDate             | [timestamp](../../development-reference/timestamp-format.md) | The date and time when the item was last modified                      |
| costcenterId             | integer                                                      | The cost center identifier to which the revenue applies                |
| totalAmount              | double                                                       | The total amount of the item including tax amount                      |
| totalDiscount            | double                                                       | The total amount of the discount                                       |
| totalSurcharge           | double                                                       | The total amount of the surcharge                                      |
| totalTaxAmount           | double                                                       | The tax amount of the item                                             |
| startDateTime            | [timestamp](../../development-reference/timestamp-format.md) | The start date and time of the item                                    |
| endDateTime              | [timestamp](../../development-reference/timestamp-format.md) | The end date and time of item                                          |
| taxDetails               | Array of [Tax Detail](get-booking.md#tax-detail)             | Individual tax details                                                 |
| dayTaxDetails            | Array of [Day Tax Detail](get-booking.md#day-tax-detail)     | The individual tax for each date. Empty when start date time is empty. |

## Service Fee

| Property        | Type                                                                            | Description                                                             |
| --------------- | ------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| id              | integer                                                                         | The unique identifier of the applied service fee                        |
| refType         | enum ([Service Fee Reference Type](get-booking.md#service-fee-reference-types)) | The item reference type to which the service fee applies                |
| refId           | integer                                                                         | The first identifier for identifying reference item in the booking      |
| ref2Id          | integer                                                                         | The second identifier for identifying the reference item in the booking |
| ref3Id          | integer                                                                         | The third identifier for identifying the reference item in the booking  |
| refDate         | [Date](../../development-reference/date-format.md)                              | The date on which the fee applies                                       |
| refCostcenterId | integer                                                                         | The reference cost centre identifier to which the fee applies           |
| amount          | double                                                                          | The amount of the service fee without tax                               |
| excludedTaxIds  | array                                                                           | The list of excluded tax ids                                            |
| createdDate     | [timestamp](../../development-reference/timestamp-format.md)                    | The date and time the product was created                               |
| modifiedDate    | [timestamp](../../development-reference/timestamp-format.md)                    | The date and time the product was last modified                         |
| totalAmount     | double                                                                          | The total amount of the service including tax                           |
| totalTaxAmount  | double                                                                          | The tax amount of the service fee                                       |
| taxDetails      | Array of [Tax Detail](get-booking.md#tax-detail)                                | Individual tax details                                                  |

## Tax Detail

| Property       | Type    | Description                                                                                                          |
| -------------- | ------- | -------------------------------------------------------------------------------------------------------------------- |
| id             | integer | The unique identifier of tax in venue                                                                                |
| tax            | double  | The amount of tax applied                                                                                            |
| rateId         | integer | The identifier of the rate that overrided the default tax rate. Zero (0) when the default tax rate is not overridden |
| rateAmount     | double  | The rate at which the tax was calculated                                                                             |
| rateAmountType | integer | The rate type of the tax. 1 = A percentage, 2 = An amount                                                            |

## Day Tax Detail

| Property   | Type                                               | Description                        |
| ---------- | -------------------------------------------------- | ---------------------------------- |
| date       | [Date](../../development-reference/date-format.md) | The day to which taxes applies     |
| taxDetails | Array of [Tax Detail](get-booking.md#tax-detail)   | Individual tax details for the day |

## Service Fee Reference Types

| Value | Description                  | Value of refId                              | Value of ref2Id                                | Value of ref3Id                                     |
| ----- | ---------------------------- | ------------------------------------------- | ---------------------------------------------- | --------------------------------------------------- |
| 1     | Booking Accommodation        | Booking Accommodation Identifier            |                                                |                                                     |
| 2     | Booking Accommodation Option | Booking Accommodation Identifier            | Booking Accommodation Option Id (roomOptionId) | Booking Accommodation Option Number (roomOptionNum) |
| 3     | Package                      | Booking Package Identifier                  |                                                |                                                     |
| 4     | Session                      | Booking Session Identifier                  |                                                |                                                     |
| 5     | Menu / Food                  | Booking Session Menu Identifier             |                                                |                                                     |
| 6     | Beverage Package             | Booking Session Beverage Package Identifier |                                                |                                                     |
| 7     | Product                      | Booking Session Product Identifier          |                                                |                                                     |
| 8     | Resource                     | Booking Session Resource Identifier         |                                                |                                                     |
| 9     | Additional Item              | Booking Additional Item Identifier          |                                                |                                                     |
| 11    | Service                      | Booking Service Identifier                  |                                                |                                                     |

## Commission By Cost Centres

| Property     | Type    | Description                                             |
| ------------ | ------- | ------------------------------------------------------- |
| costcenterId | integer | The cost center identifier to which the revenue applies |
| commission   | integer | The commission amount by Cost Centres in the Booking    |

## Booking Types

One of the following values:

| # | Description        |
| - | ------------------ |
| 1 | Simple             |
| 2 | Detailed           |
| 3 | Accommodation Only |

## Food Beverage Payable By

One of the following values:

| # | Description    |
| - | -------------- |
| 1 | Master Account |
| 2 | Guests         |

## Sales Person

| Property  | Type    | Description                               |
| --------- | ------- | ----------------------------------------- |
| id        | integer | The unique identifier of the sales person |
| firstName | string  | The first name of the sales person        |
| lastName  | string  | The last name of the sales person         |
| email     | string  | The email address of the sales person     |
| phone     | string  | The phone number of the sales person      |

## Booked By

| Property  | Type    | Description                               |
| --------- | ------- | ----------------------------------------- |
| id        | integer | The unique identifier of the co-ordinator |
| firstName | string  | The first name of the co-ordinator        |
| lastName  | string  | The last name of the co-ordinator         |
| email     | string  | The email address of the co-ordinator     |
| phone     | string  | The phone number of the co-ordinator      |

## Agent

| Property     | Type    | Description                          |
| ------------ | ------- | ------------------------------------ |
| id           | integer | The unique identifier of the company |
| businessName | integer | The business name of the company     |
| email        | string  | The email address of the company     |
| phone        | string  | The phone number of the company      |

## Menu Category

| Id | Name             |
| -- | ---------------- |
| 1  | Breakfast        |
| 2  | Lunch            |
| 3  | Dinner           |
| 4  | Coffee Break     |
| 5  | Reception        |
| 6  | Outside Catering |

## Costcenter
| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| costcenterId | integer | required | The id of costcenter |
| costPerPerson | double | required | The cost per person value of a costcenter |
| costPerPersonExcludedTaxIds | optional | array of integers | The excluded cost tax ids applied to the price of this costcenter |