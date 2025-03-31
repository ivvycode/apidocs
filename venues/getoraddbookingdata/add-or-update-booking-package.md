# Add or Update Booking Package

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="venue?action=addOrUpdateBookingPackage" %}
{% api-method-summary %}
Add or Update Booking Package
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a venue booking package.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the booking package to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation. NOTE: Additional warnings may be present to indicate issues that can occur when adding a new  package. See below for the description of these warnings.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 8821,
  "warnings": null
}
```

{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid request data that prevents the booking from being added/updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 400,
  "message": "The request contains invalid data",
  "specificCode": 24462,
  "additionalMessages": [
      "bookingId: *Value is required and can't be empty*"
  ]
}
```

{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Booking Package

| Property               | Type    | Required | Description                                                                                                             |
| :--------------------- | :------ | :------- | :---------------------------------------------------------------------------------------------------------------------- |
| id                     | integer | optional | The unique id of the booking package to update. A new booking package will be created if this parameter is not present. |
| venueId                | integer | required | The id of the venue to which the booking package belongs.                                                               |
| bookingId              | integer | required | The id of the booking to which the booking package belongs.                                                             |
| packageId              | integer | required | The id of the package to which the booking package belongs. Ignored if `id` is set.                                     |
| bookingDate            | date    | optional | Start date of the package. Ignored if `id` is set.                                                                      |
| price                  | double  | optional | The price of the booking package.                                                                                       |
| costcenters            | array of [Costcenter](add-or-update-booking-package.md#costcenter) | optional | The cost centers of the booking package. If "price" not passed this will use setup package allocation |
| mainSpaceVenueId       | integer | optional | The id of the main space venue of a booking package default session.                                                    |
| mainSpaceId            | integer | optional | The main space of the booking package default session.                                                                  |
| spaceLayoutId          | integer | optional | The space layout of the booking package default session.                                                                |
| numberAttendees        | integer | optional | The total attendees of the booking package.                                                                             |
| agreedAttendees        | integer | optional | The agreed attendees of the booking package, only applicable when the venue setting "showAdditionalAttendees" is enabled. |
| expectedAttendees      | integer | optional | The expected attendees of the booking package, only applicable when the venue setting "showAdditionalAttendees" is enabled. |
| guaranteedAttendees    | integer | optional | The guaranteed attendees of the booking package, only applicable when the venue setting "showAdditionalAttendees" is enabled. |
| setAttendees           | integer | optional | The set attendees of the booking package, only applicable when the venue setting "showAdditionalAttendees" is enabled.  |
| actualAttendees        | integer | optional | The actual attendees of the booking package, only applicable when the venue setting "showAdditionalAttendees" is enabled. |
| isAccommIncluded       | integer | optional | Whether or not accommodation is included in the booking package.                                                        |
| smallDescription       | string  | optional | The small description of the booking package.                                                                           |


## Example Request

```javascript
{
    "id": 3948,
    "venueId": 1,
    "bookingId": 26806,
    "packageId": 49,
    "price": 1300,
    "bookingDate": "2025-03-22",
    "numberAttendees": 5,
    "isAccommIncluded": true,
    "smallDescription": "test",
    "mainSpaceVenueId": 1,
    "mainSpaceId": 1,
    "spaceLayoutId": 1,
    "costcenters": [
        {
            "costcenterId": 1,
            "value": 130,
            "excludedTaxIds": null
        },
        {
            "costcenterId": 2,
            "value": 1170,
            "excludedTaxIds": []
        }
    ]
}
```

## Returns

| Property | Description                                                |
| :------- | :--------------------------------------------------------- |
| success  | Whether or not the booking package is added/updated to the booking |
| id       | The unique id of the booking package                       |
| warnings | Warning messages that can occur on success                 |

## Throws

| Code                 | Description                       |
| :------------------- | :-------------------------------- |
| Specific Code: 23026 | The booking does not exist        |
| Specific Code: 24458 | The package does not exist        |
| Specific Code: 24459 | The booking package does not exist|
| Specific Code: 24460 | An error has occurred             |
| Specific Code: 24461 | The request contains invalid data |
| Specific Code: 24462 | The request contains invalid data |

## Costcenter
| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| costcenterId | integer | required | The costcenter identifier |
| value | double | required | The cost per person for the costcenter |
| excludedTaxIds | optional | array of integers | The taxe ids excluded from the costcenter |
