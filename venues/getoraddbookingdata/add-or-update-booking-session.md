# Add or Update Booking Session

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=addOrUpdateBookingSession" %}
{% api-method-summary %}
Add or Update Booking Session
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a venue booking session. NOTE: The venue must have access to add or update booking session in order to call this api action.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the booking session to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation. NOTE: Additional warnings may be present to indicate issues that can occur when adding a new booking. See below for the description of these warnings.
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
  "specificCode": 24337,
  "additionalMessages": [
      "costcenterId: *Value is required and can't be empty*"
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Something unexpected occurred whilst processing the request. The booking session should not be expected to be added/updated.
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

## Booking Session

| Property | Type | Required | Description |  |
| :--- | :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the booking session to update. A new booking session will be created if this parameter is not present. |  |
| spaceVenueId | integer | required | The id of the venue to which the booking session belongs. |  |
| bookingId | integer | required | The id of the booking to which the new booking session will be assigned. |  |
| contactId | integer | required | The id of the booking to which the new booking session will be assigned. |  |
| name | string | required | The booking session name. Required when adding a new booking session. |  |
| minAttendeesGuaranteed | integer | optional | The total attendees of the booking session. Required when adding new booking session. |  |
| agreedAttendees | integer | optional | The agreed attendees of the booking session. |  |
| expectedAttendees | integer | optional | The expected attendees of the booking session. |  |
| guaranteedAttendees | integer | optional | The guaranteed attendees of the booking session. |  |
| setAttendees | integer | optional | The set attendees of the booking session. |  |
| actualAttendees | integer | optional | The actual attendees of the booking session. |  |
| spaceId | integer | optional | The id of the space to which the booking session belongs. |  |
| spaceLayout | integer | optional | The id of the space layout to which the booking session belongs. |  |
| customLayoutName | string | optional | The name of custom space layout. |  |
| startDate | date | required | Start date of the sesion. |  |
| startTime | string | optional | The start time of the booking session. Format is HH:mm:ss |  |
| endTime | string | optional | The end time of the booking session. Format is HH:mm:ss |  |
| setupTime | integer | optional | The setup time \(in mins\) of the booking session. |  |
| setdownTime | integer | optional | The setdown time \(in mins\) of the booking session |  |
| includeInPackage | boolean | optional | Whether or not the booking session is included in booking package. |  |
| bookingPackageId | integer | optional | The id of the booking package to which the booking session belongs. Required when | includeInPackage is true |
| tariffId | integer | optional | The tariff id to which the booking session belongs. Required when | includeInPackage is true |
| roomHireType | integer | optional | The room hire type to which the booking session belongs. Required when | includeInPackage is true |
| costcenterId | integer | optional | The id of the cost center to which the booking session belongs. Required when adding new booking session |  |
| cost | double | optional | The price of the booking session. Required when includeInPackage is false |  |
| excludedTaxIds | array | optional | The array of tax Ids which are excluded to apply on the booking session. Required when includeInPackage is false |  |

## Example Request

```javascript
{
  "venueId": 1,
  "bookingId": 15722,
  "spaceVenueId": 1,
  "name": "test",
  "contactId": 10,
  "minAttendeesGuaranteed": 10,
  "spaceId": 3,
  "spaceLayout": 0,
  "customLayoutName": "test",
  "startDate": "2020-10-28",
  "startTime": "10:00:00",
  "endTime": "11:00:00",
  "setupTime": "60",
  "setdownTime": "60",
  "includeInPackage": 0,
  "bookingPackageId": 2018,
  "tariffId": "1",
  "roomHireType": "1",
  "costcenterId": "4",
  "cost": "400",
  "excludedTaxIds": []
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the session is added/updated to the booking |
| id | The unique id of the Booking Session |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24360 | The booking does not exist |
| Specific Code: 24361 | The session does not exist |
| Specific Code: 24362 | An error has occurred |
| Specific Code: 24363 | The request contains invalid data |
| Specific Code: 24364 | The request contains invalid data |

