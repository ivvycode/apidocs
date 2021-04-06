# Change Booking Status

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=changeBookingStatus" %}
{% api-method-summary %}
Change Booking Status
{% endapi-method-summary %}

{% api-method-description %}
Changes the current status of a venue booking.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents how the status of a booking is being changed. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an operation.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 1234,
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
    "specificCode": 24397,
    "additionalMessages": [
        "convertedStageId: *Value is required and can't be empty*"
    ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Something unexpected occurred whilst processing the request. The booking status should not be expected to be updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 500,
  "message": "An error has occurred",
  "specificCode": 24346,
  "additionalMessages": []
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Request Details

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | required | The unique id of the booking whose status will be changed. |
| venueId | integer | required | The unique id of the venue to which the booking belongs. |
| currentStatus | [Current Status](change-booking-status.md#booking-status) | required | The new status to assign the booking. |
| changedByUserId | integer | optional | The unique id of the user who changed the status of the booking. The user assigned to the api key will be used when this parameter is not set. |
| cancelStageId | integer | optional | The id of the stage to assign to the opportunity when cancelling a quote \(i.e. changing from prospective to cancelled\). |
| cancelReasonId | integer | optional | The id of the stage reason to assign to the opportunity/booking being cancelled. When cancelling a quote \(i.e. changing from prospective to cancelled\), the value must belong to the "cancelStageId" stage. When cancelling a booking, the value must belong to the "cancelled" stage. |
| cancelLostToCompetition | string | optional | A description of how the cancelled booking was lost to competition. |
| cancelClosedDate | date | optional | The date when booking was cancelled. Required when the booking status is changing to cancelled. |
| convertedStageId | integer | optional | The id of the stage to assign to the opportunity to which the booking belongs. Required when changing the status to anything but cancelled. |
| convertedStageReasonId | integer | optional | The id of the stage reason to assign to the opportunity to which the booking belongs. Can be set when changing the status to anything but cancelled. |
| marketplaceStageReasonType | [Marketplace Stage Reason Type](https://github.com/ivvycode/apidocs/tree/7af24821fc40ba1f468b10f3e52c14e3bbb74fd0/venues/getoraddbookingdata/change-booking-status.mb#marketplace-stage-reason-type) | optional | This is the official regretted reason that will be sent to the booker when the opportunity is regretted. Required when "convertedStageId" is the regretted stage. |
| convertedClosedDate | date | optional | The date when quote \(ie. prospective\) is being converted to booking \(ie. Tentative or Confirmed\). Required when booking is being closed \(ie. Prospective to Tentative or Confirmed and lead stage is either won or lost\). |

## Booking Status

The following booking status options are supported.

| Value | Description |
| :--- | :--- |
| 1 | Prospective |
| 2 | Tentative |
| 3 | Confirmed |
| 4 | Cancelled |

## Marketplace Stage Reason Type

The following marketplace stage reason are supported

| Value | Description |
| :--- | :--- |
| 1 | Accommodation unavailable |
| 2 | Accommodation capacity - too small |
| 3 | Conference/Event space unavailable |
| 4 | Conference/Event space capacity - too small |
| 5 | Conference/Event space capacity - too big |
| 6 | Facilities not suitable |
| 7 | No reason given |

