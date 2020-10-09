# Add or Update Booking Session Menu

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=addOrUpdateBookingSessionMenu" %}
{% api-method-summary %}
Add or Update Booking Session Menu
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a venue booking session menu.
NOTE: The venue must have access to add or update booking session in order to call this api action.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the booking session menu to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation. NOTE: Additional warnings may be present to indicate issues that can occur when adding a new booking. See below for the description of these warnings.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 1234,
  "warnings": []
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
    "specificCode": 24337,
    "additionalMessages": [
        "costcenterId: *Value is required and can't be empty*"
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Something unexpected occurred whilst processing the request. The booking should not be expected to be added/updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 500,
  "message": "An error has occurred",
  "specificCode": 24335,
  "additionalMessages": []
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Booking Session Menu

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the booking session menu to update. A new booking session menu will be created if this parameter is not present. |
| venueId | integer | required | The unique id of the venue to which the booking session menu belongs. |
| bookingId | integer | optional | The unique id of the booking to which the new booking session menu will be assigned. |
| sessionId | integer | optional | The unique id of the booking session to which the new booking session menu will be assigned. |
| menuId | integer | optional | The unique id of the menu which is being added to the booking session |
| name | string | optional | The booking session menu name. Required when adding a new booking session menu. |
| minAttendeesGuaranteed | integer | optional | The total attendees of the booking session menu. Required when adding new booking session menu. |
| startTime | string | optional | The start time of the booking session menu. Format is HH:mm:ss |
| endTime | string | optional | The end time of the booking session menu. Format is HH:mm:ss |
| includeInPackage | boolean | optional | Whether or not the booking session is included in booking package. |
| bookingPackageId | integer | optional | The unique id of the booking package to which the booking session menu belongs. Required when includeInPackage is true |
| costcenterId | integer | optional | The unique id of the cost center to which the booking session menu belongs. Required when adding new booking session menu |
| cost | double | optional | The price of the booking session menu. Required when includeInPackage is false |
| excludedTaxIds | array | optional | The array of tax Ids which are excluded to apply on the booking session menu. Required when includeInPackage is false |
| sortOrder | integer | optional | The sort order of the booking session menu |
| items | array | optional | The array of menu items that shoud be added to menu. See [Menu Item](add-or-update-booking-session-menu.md#menu-item) section for details of each item|


## Menu Item

A booking session menu item is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| itemId | integer | required | The unique id of the menu item |
| name | string | optional | The name of the menu item. Do not pass it to automatically set the name from setup |
| quantity | integer | optional | The quantity of the menu item. Do not pass it to automatically set the quantity from setup |
| price | double | optional | The price of the *optional* menu item. |
| servingTime | string | optional | The serving time of the menu item. Format is HH:mm:ss |


### Adding/Updating items

While adding you can skip the items parameter, this will add all the non-optional menu items to the menu automatically. Passing items will only add those items to the menu including any required non-removable items.

While updating you can skip the items parameter, this will not change any of the items. Passing items will replace the items with the given items. Required non-removable items can not be removed from the menu.



