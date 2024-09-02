# Add Items To Booking

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=addItemsToBooking" method="post" summary="Add Items to Booking" %}
{% swagger-description %}
Add one or more items to a booking.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the booking belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="path" %}
The unique id of the booking to which the additional items will be added
{% endswagger-parameter %}

{% swagger-parameter name="items" type="object" in="path" %}
Array of multiple items with additional item details
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true,
  "items": [
    501
  ]
}
```
{% endswagger-response %}
{% endswagger %}

Multiple items can be added together. There must be at least one additional item.

## Example Request

```javascript
{
  "venueId": 2,
  "bookingId": 2,
  "items": [
    {
      "description": "The complete description of the additional item",
      "quantity": 10,
      "salePrice": 500,
      "salePriceHasTax": true,
      "salePriceTaxId": 2,
      "cost": 15,
      "costHasTax": true,
      "costCentreId": 5,
      "costCentreType": 2,
      "startDate": "2015-01-19 00:00:00 UTC",
      "endDate": "2015-01-22 00:00:00 UTC",
      "excludedFromCommissions": true
    }
  ]
}
```

## Additional item details

| Property                | Description                                                                                                                                                      | Type      |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| description             | The complete description of the additional item                                                                                                                  | string    |
| quantity                | The quantity of the additional item                                                                                                                              | number    |
| salePrice               | The sale price per quantity of the additional item. This amount will be interpreted as including or excluding a tax component based on the venue’s tax settings. | number    |
| salePriceHasTax         | Whether or not the sale price of the additional item has a tax component                                                                                         | boolean   |
| salePriceTaxId          | The unique identifier of the venue tax. Use getTaxList api to get the list of venue taxes.                                                                       | number    |
| cost                    | The cost per quantity of the additional item                                                                                                                     | number    |
| costHasTax              | Whether or not the cost of the additional item has a tax component                                                                                               | boolean   |
| costCentreId            | The unique identifier of the cost centre to which the additional item will be assigned                                                                           | number    |
| costCentreType          | The type of cost centre to which the additional item will be assigned                                                                                            | number    |
| startDate               | Optionally the start date of the additional item, which must fall within the dates of the booking                                                                | timestamp |
| endDate                 | Optionally the end date of the additional item, which must fall within the dates of the booking                                                                  | timestamp |
| excludedFromCommissions | Whether or not agents receive commission for the additional item                                                                                                 | boolean   |

## Returns

| Property | Description                                                                     |
| -------- | ------------------------------------------------------------------------------- |
| success  | Whether or not the items were added to the booking                              |
| items    | The unique identifiers of the additional items in the same order as the request |

## Throws

| Code                 | Description                                |
| -------------------- | ------------------------------------------ |
| Specific Code: 24140 | There must be at least one additional item |
| Specific Code: 24141 | An additional item has invalid data        |
