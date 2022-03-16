# Get Tax List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getTaxList" method="post" summary="Get Tax List" %}
{% swagger-description %}
Return the tax list for the venue.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "meta": {
    "totalResults": 1,
    "start": 0,
    "perPage": 1,
    "count": 1
  },
  "results": [
    {
      "id": 2,
      "name": "GST"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Venues Tax List`

```javascript
{
  "venueId": 2
}
```

## Returns

`A collection object with the following properties in the results`

| Property      | Type    | Description                                                                            |
| ------------- | ------- | -------------------------------------------------------------------------------------- |
| id            | integer | The unique invoice identifier                                                          |
| name          | string | The name of Tax                                                                        |
| type          | integer [Type](get-tax-list.md#type)  | The type of the tax. Whether Tax / Service Fee                                         |
| appliesTo     | integer [Applies To](get-tax-list.md#applies-to) | Whether the tax only applies to accommodation                                          |
| amountType    | integer [Amount Type](get-tax-list.md#amount-type) | Tax or service fee amount / percent to apply on items. 1 = A percentage, 2 = An amount |
| amount        | double  | Percentage / Amount of the tax                                                         |
| taxIds        | array   | The taxes which are applied to the amount of the service fee                           |
| costcenterIds | array   | The cost centers to which the tax /service fee apply                                   |
| excludedTaxIds | array   | The array of tax Ids which are excluded to apply on the booking                       |
| calculateExclusively | boolean   | If enabled, the tax will not be included in the line item totals, only in the cost centre, booking and invoice totals |
| unitType | integer [Unit Type](get-tax-list.md#unit-type)   | The metric of which to calculate the units of tax to be charged. Capacity - Max occupancy of the room. Occupants - Number of guest staying in the room, calculated from capacity or multi-occupancy values if enabled. Room Nights - Total number of room nights for the room type |

## Type

The tax types.

| Value | Description   |
| ----- | ------------ |
| 1     | Tax           |
| 2     | Service Fees  |

## Applies To

The applies to options.

| Value | Description   |
| ----- | ------------ |
| 1     | All           |
| 2     | Accommodation Only  |

## Amount Type

The amount options.

| Value | Description   |
| ----- | ------------ |
| 1     | Percentage  |
| 2     | Amount  |

## Unit Type

The unit type options.

| Value | Description   |
| ----- | ------------ |
| 1     | Room Nights  |
| 2     | Capacity  |
| 3     | Occupancy  |