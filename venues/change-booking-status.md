# Change Booking Status

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=changeBookingStatus" %}
{% api-method-summary %}
Change Booking Status
{% endapi-method-summary %}

{% api-method-description %}
Updates the current status of the booking
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The unique id of the booking to be updated
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking belongs
{% endapi-method-parameter %}

{% api-method-parameter name="accountId" type="integer" required=true %}
The unique id of the booking to which the booking status will be added
{% endapi-method-parameter %}

{% api-method-parameter name="currentStatus" type="integer" required=true %}
The status to assign the booking. See [Current Status](change-booking-status.md#booking-status).
{% endapi-method-parameter %}

{% api-method-parameter name="cancelStageId" type="integer" required=false %}
The id of the cancel stage. Required when booking is being cancelled and current status is prospective.
{% endapi-method-parameter %}

{% api-method-parameter name="cancelReasonId" type="integer" required=false %}
The id of the cancel reason. It should be one of the reason of cancelStageId. Required when booking is being cancelled.
{% endapi-method-parameter %}

{% api-method-parameter name="cancelLostToCompetition" type="string" required=false %}
The description for cancelling the booking
{% endapi-method-parameter %}

{% api-method-parameter name="cancelClosedDate" type="Date" required=false %}
The date when booking was cancelled. Required when booking is being cancelled
{% endapi-method-parameter %}

{% api-method-parameter name="convertedStageId" type="integer" required=false %}
The id of the stage. This stage will be assigned to associated opportunity. Required when booking is converted to Confirmed, Tentative or Prospective.
{% endapi-method-parameter %}

{% api-method-parameter name="convertedStageReasonId" type="integer" required=false %}
The id of the stage reason. This stage reason will be assigned to associated opportunity.
{% endapi-method-parameter %}

{% api-method-parameter name="marketplaceStageReasonType" type="integer" required=false %}
This is the official regretted reason that will be sent to the booker when the opportunity is regretted. Required when convertedStageId is regretted. See [Marketplace Stage Reason Type](change-booking-status.mb#marketplace-stage-reason-type).
{% endapi-method-parameter %}

{% api-method-parameter name="cancelClosedDate" type="Date" required=false %}
The date when booking was closed. Required when booking is being closed (ie. Stage is either won or lost).
{% endapi-method-parameter %}

{% api-method-parameter name="paymentTermId" type="integer" required=false %}
The id of the payment term to add payment term in booking. It will not change anything if booking already have a payment term.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
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


