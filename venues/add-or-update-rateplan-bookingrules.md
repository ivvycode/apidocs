# Add or Update Rate Plan Booking Rules

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateRatePlanBookingRules" path="" %}
{% api-method-summary %}
Add or Update Rate Plan Booking Rules 
{% endapi-method-summary %}

{% api-method-description %}
Add or Update the booking rules of venue rate plans
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the rate plan belongs
{% endapi-method-parameter %}

{% api-method-parameter name="barId" type="integer" required=true %}
The unique id of the rate plan to which the booking rule applies
{% endapi-method-parameter %}

{% api-method-parameter name="roomId" type="integer" required=true %}
The unique id of the room to which the booking rule applies
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="string" required=true %}
The start date from which the booking rule will apply
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="string" required=true %}
The end date until which the booking rule will apply
{% endapi-method-parameter %}

{% api-method-parameter name="closeOutStatus" type="object" required=true %}
The close out status of the booking rule from startDate to End Date
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "success": true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

NOTE: The dynamic data is only available to venues that integrate with a distribution channel.

## Examples

### Setting the rate plan booking rules for a single date

**REQUEST**

```javascript
{
  "venueId": 123,
  "barId": 456,
  "roomId": 789,
  "startDate": "2018-07-27",
  "endDate": "2018-07-27",
  "closeOutStatus": 2  
}
```

### Setting the rate plan booking rules for a date range

**REQUEST**

```javascript
{
  "venueId": 123,
  "barId": 456,
  "roomId": 789,
  "startDate": "2018-07-27",
  "endDate": "2018-08-03",
  "closeOutStatus": 2  
}
```

## Returns

| Property | Description | Type |
| --- | --- | --- |
| success | Whether or not the rate plan booking rules were updated | boolean |

## Close Out Status

The following close out status values are supported by the current booking rules.

| Value | Description |
| --- | --- |
| 1 | The room is open for bookings |
| 2 | The room is closed for bookings |

