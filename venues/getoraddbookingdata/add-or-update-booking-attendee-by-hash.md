# Add or Update Booking Attendee (By Hash)

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=addOrUpdateBookingAttendeeByHash" %}
{% api-method-summary %}
Add or Update Booking Attendee
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a venue booking attendee. NOTE: The venue must have access to add or update booking attendee in order to call this api action.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the booking attendee to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 8821,
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
  "specificCode": 24413,
  "additionalMessages": [
      "firstName: *Value is required and can't be empty*"
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Something unexpected occurred whilst processing the request. The booking attendee should not be expected to be added/updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 500,
  "message": "An error has occurred",
  "specificCode": 24412,
  "additionalMessages": []
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Booking Attendee

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| hash | string | optional | The unique hash of the booking attendee to update. A new booking attendee will be created if this parameter is not present. |
| venueId | integer | required | The id of the venue to which the booking attendee belongs |
| bookingId | integer | required | The id of the booking to which the new booking attendee will be assigned. |
| firstName | string | required | The first name of the booking attendee. |
| lastName | string | required | The last name of the booking attendee. |
| phone | string | required | The phone number of the booking attendee. |
| email | string | required | The email address of the booking attendee. |
| dietaryRequirement | string | optional | The dietary requirements of the booking attendee. |
| menuItems | array | optional | The list of menu items that is included in the booking attendee menu. See [Menu Item](add-or-update-booking-attendee.md#menu-item) section for details of each item  |

## Menu Item

A menu item is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| sessionId | integer | required | The id of the session to which the booking menu belongs |
| menuId | integer | required | The id of the attendee to which the booking attendee belongs |
| inventoryId | integer | required | The id of the attendee to which the booking attendee belongs |

### Updating items

While updating you can skip the menuItems parameter, this will not change any of the menu items. Passing menuItems will replace the menu items with the given items.


## Example Request

```javascript
{
    "venueId": 1,
    "bookingId": 4407,
    "firstName": "First Name",
    "lastName": "Last Name",
    "phone": "123456",
    "dietaryRequirement": "Something required for my diet",
    "email" : "test@email.com",
    "menuItems": [
    {
        "sessionId": "2447",
        "menuId": 225,
        "inventoryId": 14
    },
    {
        "sessionId": "2447",
        "menuId": 225,
        "inventoryId": 15
    },
    {
        "sessionId": "2448",
        "menuId": 226,
        "inventoryId": 16
    }
  ]
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the booking attendee was added/updated |
| id | The unique id of the booking attendee that was added/updated |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24410 | The booking does not exist |
| Specific Code: 24411 | The booking attendee does not exist |
| Specific Code: 24412 | An error has occurred |
| Specific Code: 24413 | The request contains invalid data |
| Specific Code: 24414 | The request contains invalid data |

