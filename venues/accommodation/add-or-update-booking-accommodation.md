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
Invalid request data that prevents the accommodation group from being added/updated.
{% endapi-method-response-example-description %}
```javascript
{
  "errorCode": 400,
  "message": "The request contains invalid data",
  "specificCode": 24248,
  "additionalMessages": [
      "2019-01-01: The number of rooms can't exceed 30"
  ],
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
