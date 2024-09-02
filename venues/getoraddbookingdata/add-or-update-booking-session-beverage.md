# Add or Update Booking Session Beverage

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="venue?action=addOrUpdateBookingSessionBeverage" %}
{% api-method-summary %}
Add or Update Booking Session Beverage
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a venue booking session beverages. NOTE: The venue must have access to add or update booking session beverage in order to call this api action.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the booking session beverage to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 1234
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
    "specificCode": 24354,
    "additionalMessages": [
        "costcenterId: *Value is required and can't be empty*"
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Something unexpected occurred whilst processing the request. The booking session beverage should not be expected to be added/updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 500,
  "message": "An error has occurred",
  "specificCode": 24353,
  "additionalMessages": []
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Booking Session Beverage

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the booking session beverage package to update. A new booking session beverage will be created if this parameter is not present. |
| venueId | integer | required | The unique id of the venue to which the booking session beverage package belongs. |
| bookingId | integer | optional | The unique id of the booking to which the new booking session beverage package will be assigned. |
| sessionId | integer | optional | The unique id of the booking session to which the new booking session beverage package will be assigned. |
| beverageId | integer | optional | The unique id of the beverage package which is being added to the booking session |
| name | string | optional | The booking session beverage package name. Required when adding a new booking session beverage package. |
| minAttendeesGuaranteed | integer | optional | The total attendees of the booking session beverage package. Required when adding new booking session beverage package. |
| startTime | string | optional | The start time of the booking session beverage package. Format is HH:mm:ss |
| endTime | string | optional | The end time of the booking session beverage package. Format is HH:mm:ss |
| includeInPackage | boolean | optional | Whether or not the booking session beverage package is included in booking package. |
| bookingPackageId | integer | optional | The unique id of the booking package to which the booking session beverage package belongs. Required when includeInPackage is true. |
| costcenterId | integer | optional | The unique id of the cost center to which the booking session beverage package belongs. Required when adding new booking session beverage package. |
| cost | double | optional | The price of the booking session beverage package. Required when includeInPackage is false. |
| excludedTaxIds | array | optional | The array of tax Ids which are excluded to apply on the booking session beverage package. Required when includeInPackage is false. |
| costPeriod | integer | optional | The period of the cost of the booking session beverage package. Required when the selected beverage package is hourly. 1 = Hourly, 2 = Daily |
| numHours | float | optional | The number of hours of the booking session beverage needed. Required when the cost period is hourly. The value must match with one of the hours added in Venue Setup &gt; Beverages &gt; Packages &gt; Hourly Prices. For example, for 3 hours and 45 minutes, pass 3.75. |
| sortOrder | integer | optional | The sort order of the booking session beverage package. |
| excludedFromCommissions | boolean | optional | Whether this booking session beverage excluded from commission. Only applicable when booking is commissionable. Default is true. |
| items | array | optional | The array of beverage package items that shoud be added to beverage package. See [Beverage Item](add-or-update-booking-session-beverage.md#beverage-item) section for details of each item |

## Beverage Item

A booking session beverage item is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| itemId | integer | required | The unique id of the beverage item |
| name | string | optional | The name of the beverage item. Do not pass it to automatically set the name from setup |
| quantity | integer | optional | The quantity of the beverage item. Do not pass it to automatically set the quantity from setup |
| price | double | optional | The price of the _optional_ beverage item. |

### Adding/Updating items

While adding you can skip the items parameter, this will add all the non-optional beverge items to the beverage package automatically. Passing items will only add those items to the beverage package including any required non-removable items.

While updating you can skip the items parameter, this will not change any of the items. Passing items will replace the items with the given items. Required non-removable items cannot be removed from the beverage package.

