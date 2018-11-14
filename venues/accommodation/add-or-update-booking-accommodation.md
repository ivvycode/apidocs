# Add or Update Booking Accommodation

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=addOrUpdateBookingAccommodation" %}
{% api-method-summary %}
Add or Update Booking Accommodation
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a specific booking accommodation group on a specific venue booking.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the accommodation group to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation.
{% endapi-method-response-example-description %}
```javascript
{
  "success": true,
  "id": 1423
}
```
{% endapi-method-response-example %}
{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Failure to add or update the accommodation with a general error message, or a message that applies to specific request data.
{% endapi-method-response-example-description %}
```javascript
{
  "errorCode": 400,
  "message": "The booking details were not updated",
  "specificCode": 24248
}
```
```javascript
{
  "errorCode": 400,
  "message": "endDate: The end date must be after the start date",
  "specificCode": 24249
}
```
{% endapi-method-response-example %}
{% endapi-method-response-example %}
{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Failure for an unknown and/or unexpected error.
{% endapi-method-response-example-description %}
```javascript
{
  "errorCode": 500,
  "message": "An unknown error has occurred",
  "specificCode": 24250
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
