---
description: >-
  Note: Section sessions, packages, additionalItems, beveragePackages, menus,
  resources, products and serviceFees are not published yet.
---

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getBooking" method="post" %}
{% swagger-description %}
Get the details of a specific booking to which the user has access.
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="body" %}
The id of the booking
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "id": 36160,
  "venueId": 1,
  "code": "4EQBCB2CCW",
  "name": "Booking Test",
  "eventType": "Conference",
  "eventTypeId": 3,
  "eventSubTypeId": null,
  "companyId": 773,
  "company": {
      "id": 773,
      "businessName": "My Company Co."
  },
  "contactId": 6892,
  "contact": {
      "id": 6892,
      "firstName": "Jon",
      "lastName": "A",
      "email": "john.a@b.com",
      "phone": "123"
  },
  "isConfidential": false,
  "currentStatus": 2,
  "totalAmount": 131,
  "totalTaxAmount": 10.25,
  "amountOutstanding": 131,
  "accountTimezone": "Australia/Brisbane",
  "venueTimezone": "Australia/Brisbane",
  "createdDate": "2026-07-06 01:41:51 UTC",
  "modifiedDate": "2026-07-06 01:41:51 UTC",
  "lastModifiedDate": "2026-07-06 01:44:26 UTC",
  "bookingType": 1,
  "dateEventStart": "2026-03-31 00:00:00 UTC",
  "dateEventEnd": "2026-03-31 00:00:00 UTC",
  "convertedToTentative": "2026-07-06 01:41:51 UTC",
  "convertedToConfirmed": "",
  "convertedToCancelled": "",
  "convertedToProspectiveHold": "",
  "isAccommIncluded": false,
  "dateAccomStart": "",
  "dateAccomEnd": "",
  "focRoomsDenominator": 0,
  "maxNumFocRoomsPerDay": 0,
  "hasPackages": true,
  "decisionDate": "",
  "canBeMoved": false,
  "bookedById": 1,
  "beoNumbers": [],
  "isBeoFinalised": false,
  "beoFinalisedDate": "",
  "otaFolioRef": null,
  "accommCutOffDate": "",
  "accommReservationMethod": [],
  "accommCancellationDate": "",
  "accommChargingMethod": 0,
  "accommGuaranteeRequired": false,
  "accommExternalBlockId": "BLOCKID",
  "revenueTemplateId": null,
  "hasCommissions": false,
  "hasCommissionPaid": false,
  "agentCompanyId": 0,
  "agentCompany": null,
  "agentContactId": 0,
  "agentContact": null,
  "commissionAccommodationType": 2,
  "commissionAccommodation": null,
  "commissionSpaceType": 2,
  "commissionSpace": null,
  "commissionFoodType": 2,
  "commissionFood": 0,
  "commissionBeverageType": 2,
  "commissionBeverage": 0,
  "commissionAudioVisualType": 2,
  "commissionAudioVisual": null,
  "dailyRevenue": [
      {
          "venueId": 1,
          "costcenterId": 1,
          "revenueDate": "2026-03-31",
          "totalAmount": 27.5,
          "totalDiscountAmount": 0,
          "totalTaxAmount": 2.5
      },
      {
          "venueId": 1,
          "costcenterId": 2,
          "revenueDate": "2026-03-31",
          "totalAmount": 26.25,
          "totalDiscountAmount": 0,
          "totalTaxAmount": 1.25
      },
      {
          "venueId": 1,
          "costcenterId": 3,
          "revenueDate": "2026-03-31",
          "totalAmount": 44,
          "totalDiscountAmount": 0,
          "totalTaxAmount": 4
      },
      {
          "venueId": 1,
          "costcenterId": 4,
          "revenueDate": "2026-03-31",
          "totalAmount": 27.5,
          "totalDiscountAmount": 0,
          "totalTaxAmount": 2.5
      },
      {
          "venueId": 1,
          "costcenterId": 5,
          "revenueDate": "2026-03-31",
          "totalAmount": 0,
          "totalDiscountAmount": 0,
          "totalTaxAmount": 0
      }
  ],
  "packages": [
      {
          "id": 7861,
          "bookingDate": "2026-03-31",
          "numberAttendees": 10,
          "price": 100,
          "createdDate": "2026-07-06 01:41:51 UTC",
          "modifiedDate": "2026-07-06 01:41:52 UTC",
          "totalAmount": 108.75,
          "totalDiscount": 0,
          "totalSurcharge": 0,
          "totalTaxAmount": 8.75,
          "priceMethod": 2,
          "costcenters": [
              {
                  "costcenterId": 1,
                  "value": 25,
                  "discount": 0,
                  "surcharge": 0,
                  "totalAmount": 27.5,
                  "totalSurcharge": 0,
                  "totalTaxAmount": 2.5,
                  "taxDetails": [
                      {
                          "id": 1,
                          "tax": 2.5,
                          "rateId": 0,
                          "rateAmount": 10,
                          "rateAmountType": 1
                      }
                  ]
              },
              {
                  "costcenterId": 2,
                  "value": 25,
                  "discount": 0,
                  "surcharge": 0,
                  "totalAmount": 26.25,
                  "totalSurcharge": 0,
                  "totalTaxAmount": 1.25,
                  "taxDetails": [
                      {
                          "id": 1,
                          "tax": 1.25,
                          "rateId": 13,
                          "rateAmount": 5,
                          "rateAmountType": 1
                      }
                  ]
              },
              {
                  "costcenterId": 3,
                  "value": 25,
                  "discount": 0,
                  "surcharge": 0,
                  "totalAmount": 27.5,
                  "totalSurcharge": 0,
                  "totalTaxAmount": 2.5,
                  "taxDetails": [
                      {
                          "id": 1,
                          "tax": 2.5,
                          "rateId": 0,
                          "rateAmount": 10,
                          "rateAmountType": 1
                      }
                  ]
              },
              {
                  "costcenterId": 4,
                  "value": 25,
                  "discount": 0,
                  "surcharge": 0,
                  "totalAmount": 27.5,
                  "totalSurcharge": 0,
                  "totalTaxAmount": 2.5,
                  "taxDetails": [
                      {
                          "id": 1,
                          "tax": 2.5,
                          "rateId": 0,
                          "rateAmount": 10,
                          "rateAmountType": 1
                      }
                  ]
              },
              {
                  "costcenterId": 5,
                  "value": 0,
                  "discount": 0,
                  "surcharge": 0,
                  "totalAmount": 0,
                  "totalSurcharge": 0,
                  "totalTaxAmount": 0,
                  "taxDetails": []
              }
          ],
          "taxDetails": [
              {
                  "id": 1,
                  "tax": 7.5,
                  "rateId": 0,
                  "rateAmount": 10,
                  "rateAmountType": 1
              },
              {
                  "id": 1,
                  "tax": 1.25,
                  "rateId": 13,
                  "rateAmount": 5,
                  "rateAmountType": 1
              }
          ],
          "smallDescription": "sdsd",
          "packageId": 7,
          "packageName": "Premium - Flat rate"
      }
  ],
  "sessions": [
      {
          "id": 20261,
          "name": "Morning",
          "startDate": "2026-03-31",
          "endDate": "2026-03-31",
          "startTime": "15:00:00",
          "endTime": "17:00:00",
          "spaceVenueId": 1,
          "spaceId": 1,
          "spaceLayout": 0,
          "customLayoutName": "C",
          "tariffId": null,
          "cost": 0,
          "discount": 0,
          "surcharge": 0,
          "totalAmount": 0,
          "totalDiscount": 0,
          "totalSurcharge": 0,
          "totalTaxAmount": 0,
          "costcenterId": 0,
          "includeInPackage": true,
          "bookingPackageId": 7861,
          "beoNumbers": [],
          "createdDate": "2026-07-06 01:41:51 UTC",
          "modifiedDate": "2026-07-06 01:41:52 UTC",
          "taxDetails": [],
          "totalAttendees": 10,
          "projectedSpend": []
      }
  ],
  "menus": [
      {
          "id": 2742,
          "name": "Lunch",
          "menuVenueId": 1,
          "menuId": 1,
          "menuTypeCategory": 0,
          "sessionId": 20261,
          "cost": 0,
          "discount": 0,
          "surcharge": 0,
          "excludedTaxIds": [],
          "startDate": "2026-03-31",
          "endDate": "2026-03-31",
          "startTime": "08:00:00",
          "endTime": "20:00:00",
          "includeInPackage": true,
          "bookingPackageId": 7861,
          "createdDate": "2026-07-06 01:41:51 UTC",
          "modifiedDate": "2026-07-06 01:41:52 UTC",
          "costcenterId": 0,
          "totalAmount": 0,
          "totalDiscount": 0,
          "totalSurcharge": 0,
          "totalTaxAmount": 0,
          "taxDetails": [],
          "totalAttendees": 10,
          "costcenters": []
      }
  ],
  "beveragePackages": [
      {
          "id": 3191,
          "name": "Morning tea",
          "sessionId": 20261,
          "beverageVenueId": 1,
          "beverageId": 1,
          "cost": 0,
          "discount": 0,
          "surcharge": 0,
          "startDate": "2026-03-31",
          "endDate": "2026-03-31",
          "startTime": "08:00:00",
          "endTime": "20:00:00",
          "includeInPackage": true,
          "bookingPackageId": 7861,
          "createdDate": "2026-07-06 01:41:51 UTC",
          "modifiedDate": "2026-07-06 01:41:52 UTC",
          "costcenterId": 0,
          "totalAmount": 0,
          "totalDiscount": 0,
          "totalSurcharge": 0,
          "totalTaxAmount": 0,
          "taxDetails": [],
          "totalAttendees": 10,
          "smallDescription": "Morning maza",
          "marketplaceName": "Hourly Price"
      }
  ],
  "resources": [
      {
          "id": 5713,
          "name": "Resource 1",
          "sessionId": 20261,
          "resourceVenueId": 1,
          "resourceId": 8,
          "cost": 0,
          "discount": 0,
          "surcharge": 0,
          "quantity": 10,
          "startDate": "2026-03-31",
          "endDate": "2026-03-31",
          "startTime": "15:00:00",
          "endTime": "17:00:00",
          "includeInPackage": true,
          "bookingPackageId": 7861,
          "createdDate": "2026-07-06 01:41:51 UTC",
          "modifiedDate": "2026-07-06 01:41:52 UTC",
          "costcenterId": 0,
          "totalAmount": 0,
          "totalDiscount": 0,
          "totalSurcharge": 0,
          "totalTaxAmount": 0,
          "taxDetails": []
      },
      {
          "id": 5714,
          "name": "Resource 2",
          "sessionId": 20261,
          "resourceVenueId": 76,
          "resourceId": 4,
          "cost": 0,
          "discount": 0,
          "surcharge": 0,
          "quantity": 1,
          "startDate": "2026-03-31",
          "endDate": "2026-03-31",
          "startTime": "15:00:00",
          "endTime": "17:00:00",
          "includeInPackage": false,
          "bookingPackageId": 7861,
          "createdDate": "2026-07-06 01:41:51 UTC",
          "modifiedDate": "2026-07-06 01:41:52 UTC",
          "costcenterId": 3,
          "totalAmount": 0,
          "totalDiscount": 0,
          "totalSurcharge": 0,
          "totalTaxAmount": 0,
          "taxDetails": []
      }
  ],
  "products": [
      {
          "id": 1597,
          "name": "Product",
          "sessionId": 20261,
          "productId": 13,
          "cost": 5,
          "discount": 0,
          "surcharge": 0,
          "quantity": 1,
          "includeInPackage": false,
          "bookingPackageId": 0,
          "createdDate": "2026-07-06 01:44:14 UTC",
          "modifiedDate": "2026-07-06 01:44:26 UTC",
          "costcenterId": 3,
          "totalAmount": 5.5,
          "totalDiscount": 0,
          "totalSurcharge": 0,
          "totalTaxAmount": 0.5,
          "taxDetails": [
              {
                  "id": 1,
                  "tax": 0.5,
                  "rateId": 0,
                  "rateAmount": 10,
                  "rateAmountType": 1
              }
          ]
      }
  ],
  "additionalItems": [
      {
          "id": 4066,
          "description": "Test Item",
          "quantity": 1,
          "totalCost": 10,
          "totalCostDiscount": 0,
          "totalCostSurcharge": 0,
          "actualCost": 0,
          "createdDate": "2026-07-06 01:42:21 UTC",
          "modifiedDate": "2026-07-06 01:42:21 UTC",
          "costcenterId": 3,
          "totalAmount": 11,
          "totalDiscount": 0,
          "totalSurcharge": 0,
          "totalTaxAmount": 1,
          "startDateTime": "",
          "endDateTime": "",
          "taxDetails": [
              {
                  "id": 1,
                  "tax": 1,
                  "rateId": 0,
                  "rateAmount": 10,
                  "rateAmountType": 1
              }
          ],
          "dayTaxDetails": []
      }
  ],
  "serviceFees": [
      {
          "id": 31482,
          "refType": 3,
          "refId": 7861,
          "ref2Id": 0,
          "ref3Id": 0,
          "refDate": "2026-03-31",
          "refCostcenterId": 1,
          "amount": 1.25,
          "createdDate": "2026-07-06 01:41:52 UTC",
          "modifiedDate": "2026-07-06 01:41:54 UTC",
          "totalAmount": 1.25,
          "totalTaxAmount": 0,
          "taxDetails": []
      },
      {
          "id": 31484,
          "refType": 3,
          "refId": 7861,
          "ref2Id": 0,
          "ref3Id": 0,
          "refDate": "2026-03-31",
          "refCostcenterId": 2,
          "amount": 1.25,
          "createdDate": "2026-07-06 01:41:52 UTC",
          "modifiedDate": "2026-07-06 01:41:54 UTC",
          "totalAmount": 1.25,
          "totalTaxAmount": 0,
          "taxDetails": []
      },
      {
          "id": 31486,
          "refType": 3,
          "refId": 7861,
          "ref2Id": 0,
          "ref3Id": 0,
          "refDate": "2026-03-31",
          "refCostcenterId": 3,
          "amount": 1.25,
          "createdDate": "2026-07-06 01:41:52 UTC",
          "modifiedDate": "2026-07-06 01:41:54 UTC",
          "totalAmount": 1.25,
          "totalTaxAmount": 0,
          "taxDetails": []
      },
      {
          "id": 31488,
          "refType": 3,
          "refId": 7861,
          "ref2Id": 0,
          "ref3Id": 0,
          "refDate": "2026-03-31",
          "refCostcenterId": 4,
          "amount": 1.25,
          "createdDate": "2026-07-06 01:41:52 UTC",
          "modifiedDate": "2026-07-06 01:41:54 UTC",
          "totalAmount": 1.25,
          "totalTaxAmount": 0,
          "taxDetails": []
      },
      {
          "id": 31490,
          "refType": 9,
          "refId": 4066,
          "ref2Id": 0,
          "ref3Id": 0,
          "refDate": "2026-03-31",
          "refCostcenterId": 3,
          "amount": 0.5,
          "createdDate": "2026-07-06 01:42:22 UTC",
          "modifiedDate": "2026-07-06 01:42:22 UTC",
          "totalAmount": 0.5,
          "totalTaxAmount": 0,
          "taxDetails": []
      },
      {
          "id": 31498,
          "refType": 7,
          "refId": 1597,
          "ref2Id": 0,
          "ref3Id": 0,
          "refDate": "2026-03-31",
          "refCostcenterId": 3,
          "amount": 0.25,
          "createdDate": "2026-07-06 01:44:14 UTC",
          "modifiedDate": "2026-07-06 01:44:26 UTC",
          "totalAmount": 0.25,
          "totalTaxAmount": 0,
          "taxDetails": []
      }
  ],
  "customFields": [
      {
          "fieldId": 1,
          "displayName": "Small Text",
          "fieldValue": null
      },
      {
          "fieldId": 5,
          "displayName": "Booking Field",
          "fieldValue": null
      },
      {
          "fieldId": 8,
          "displayName": "Response Due Date",
          "fieldValue": null
      },
      {
          "fieldId": 9,
          "displayName": "Decision Due Date",
          "fieldValue": null
      }
  ],
  "salesPersonUser": null,
  "bookedByUser": {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": "john.doe@iv.com",
      "phone": ""
  },
  "leadBccEmail": null,
  "foodBeveragePayableBy": 1,
  "totalAttendees": 10,
  "agent": null,
  "commissionByCostCentres": [
      {
          "costcenterId": 1,
          "commission": 0
      },
      {
          "costcenterId": 2,
          "commission": 0
      },
      {
          "costcenterId": 3,
          "commission": 0
      },
      {
          "costcenterId": 4,
          "commission": 0
      },
      {
          "costcenterId": 5,
          "commission": 0
      }
  ],
  "opportunityId": null,
  "hasCateringWebsite": false,
  "cateringWebsiteLogoId": null,
  "cateringWebsiteLogo": null,
  "cateringWebsiteBannerId": null,
  "cateringWebsiteBanner": null,
  "cateringWebsiteEventDesc": null,
  "cateringWebsiteEndNumDays": null,
  "externalUrls": [
    {
        "ref": "sales-force",
        "url": "https://salesforce.com",
        "label": "Sales force"
    }
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
| eventSubTypeId          | integer                                                                       | The event sub type id of the booking                                                                                                                            |
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
| hasCommissions           | boolean   | Whether or not the booking has commissions                                                                                 |
| hasCommissionPaid        | boolean   | The commission has been paid for the Booking                                                                              |
| agentCompanyId           | integer   | The id of the revenue template applied to the booking                                                                     |
| agentCompany             | [Company](get-booking.md#company) | The details of the agent company assigned to the booking                                                                  |
| agentContactId           | integer   | The id of the revenue template applied to the booking                                                                     |
| agentContact             | [Contact](get-booking.md#contact) | The details of the agent contact assigned to the booking                                                                  |
| commissionAccommodationType      | integer   | The [Commission Type](get-booking.md#commission-type) for accommodation                                                                                    |
| commissionAccommodation  | double    | The amount of commission for accommodation                                                                              |
| commissionSpaceType      | integer   | The [Commission Type](get-booking.md#commission-type) for space                                                                                    |
| commissionSpace          | double    | The amount of commission for space                                                                                        |
| commissionFoodType       | integer   | The [Commission Type](get-booking.md#commission-type) for food                                                                                     |
| commissionFood           | double    | The amount of commission for food                                                                                         |
| commissionBeverageType   | integer   | The [Commission Type](get-booking.md#commission-type) for beverage                                                                                 |
| commissionBeverage       | double    | The amount of commission for beverage                                                                                     |
| commissionAudioVisualType| integer   | The [Commission Type](get-booking.md#commission-type) for audio visual                                                                             |
| commissionAudioVisual    | double    | The amount of commission for audio visual                                                                                 |
| dailyRevenue            | Array of [DailyRevenue](get-booking.md#daily-revenue)                            | The daily revenue data of booking                                                                                                                           |
| packages                | Array of [Package](get-booking.md#package)                                       | The list of packages of the booking                                                                                                                         |
| sessions                | Array of [Session](get-booking.md#session)                                       | The list of sessions of booking                                                                                                                             |
| menus                   | Array of [Menu](get-booking.md#menu)                                             | The list of menus of the booking                                                                                                                            |
| beveragePackages        | Array of [Beverage Package](get-booking.md#beverage-package)                     | The list of beverage packages of the booking                                                                                                                |
| resources               | Array of [Resource](get-booking.md#resource)                                         | The list of resources of the booking                                                                                                                        |
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
| bookingType             | enum ([Booking Types](get-booking.md#booking-types))              | The type of Booking selected for the Booking                                                                                                                |
| opportunityId           | integer                                                                          | The id of the Opportunity for the Booking                                                                                                                   |
| hasCateringWebsite | boolean | Whether or not the catering website is enabled for the booking |
| cateringWebsiteLogoId | string | The catering website logo for the booking |
| cateringWebsiteLogo | [File](get-booking.md#file) | The catering website logo for the booking |
| cateringWebsiteBannerId | string | The catering website banner for the booking |
| cateringWebsiteBanner | [File](get-booking.md#file) | The catering website banner for the booking |
| cateringWebsiteEventDesc | string | The catering website event description for the booking |
| cateringWebsiteEndNumDays | integer | The catering website end num days from event start for the booking |
| externalUrls | Array of [ExternalUrl](get-booking.md#external-url-field) | This is an array of External URL field objects of the booking. |


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
| projectedSpend   | object                                                       | The [projected spend](get-booking-session-list.md#projected-spend) of the session                       |

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
| resourceVenueId  | integer                                                      | The venue identifier to which the resource belongs. This can be different than booking's venue id             |
| resourceId       | integer                                                      | The reference resource identifier in venue resources             |
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
| productId        | integer                                                      | The reference product identifier in venue products               |
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
| 3 | Simple             |
| 1 | Detailed           |
| 4 | Accommodation Only |

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

## External URL Field

An External URL field is an object with the following details.

| Property | Type   | Description                                                                                                                                              |
| -------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ref      | string | The unique reference key of the external URL                                                                                                             |
| url      | string | The url link (https) scheme eg. https://example.com                                                                                                      |
| label    | string | The label of the URL to display.                                                                                                                         |

## Commission Type

One of the following values:

| # | Description    |
| - | -------------- |
| 1 | Fixed          |
| 2 | Percentage     |