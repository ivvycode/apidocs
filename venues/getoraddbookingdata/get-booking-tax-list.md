# Get Tax List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getBookingTaxList" method="post" summary="Get Booking Tax List" %}
{% swagger-description %}
Return the tax list for the venue booking.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="path" %}
The id of the venue booking
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of booking taxes to get in a single call
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 6,
        "start": 0,
        "perPage": 1,
        "count": 1
    },
    "results": [
        {
            "id": 648,
            "venueId": 1,
            "bookingId": 2,
            "venueTaxId": 1,
            "name": "GST",
            "type": 1,
            "appliesTo": 1,
            "amountType": 1,
            "amount": 7.5,
            "taxIds": [],
            "excludedTaxIds": [],
            "costcenterIds": [
                1,
                2,
            ],
            "calculateExclusively": false,
            "unitType": 1
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Booking Tax List`

```javascript
{
  "venueId": 1,
  "perPage":1,
  "bookingId": 2
}
```

## Returns

`A collection object with the following properties in the results`

| Property      | Type    | Description                                                                            |
| ------------- | ------- | -------------------------------------------------------------------------------------- |
| id            | integer | The unique invoice identifier                                                          |
| venueId       | integer | The unique identifier of the venue belongs to the booking tax                                                          |
| bookingId     | integer | The unique identifier of the booking belongs to the booking tax |
| name          | string | The name of Tax                                                                        |
| type          | integer [Type](../venuedata/get-tax-list.md) | The type of the tax. Whether Tax / Service Fee                                         |
| appliesTo     | integer [Applies To](../venuedata/get-tax-list.md#applies-to) | Whether the tax only applies to accommodation                                          |
| amountType    | integer [Amount Type](../venuedata/get-tax-list.md#amount-type) | Tax or service fee amount / percent to apply on items. 1 = A percentage, 2 = An amount |
| amount        | double  | Percentage / Amount of the tax                                                         |
| taxIds        | array   | The taxes which are applied to the amount of the service fee                           |
| costcenterIds | array   | The cost centers to which the tax /service fee apply                                   |
| excludedTaxIds | array   | The array of tax Ids which are excluded to apply on the booking                       |
| calculateExclusively | boolean   | If enabled, the tax will not be included in the line item totals, only in the cost centre, booking and invoice totals |
| unitType | integer  [Unit Type](../venuedata/get-tax-list.md#unit-type) | The metric of which to calculate the units of tax to be charged. Capacity - Max occupancy of the room. Occupants - Number of guest staying in the room, calculated from capacity or multi-occupancy values if enabled. Room Nights - Total number of room nights for the room type |
