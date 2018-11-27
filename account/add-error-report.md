# Add Error Report

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/account?action=addErrorReport" path="" %}
{% api-method-summary %}
Add Error Report
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="code" type="string" required=true %}
The distinguish code of error report
{% endapi-method-parameter %}

{% api-method-parameter name="message" type="string" required=true %}
Th message description of an error  report
{% endapi-method-parameter %}

{% api-method-parameter name="level" type="integer" required=true %}
The severity level of an error report
{% endapi-method-parameter %}

{% api-method-parameter name="refType" type="integer" required=true %}
The [type](add-error-report.md#reftype) of the error report e.g. booking, accommodation group..
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=false %}
The unique venue id of related error report
\(Required for venue booking error\)
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=false %}
The unique booking id of related error report
\(Required for venue booking error\)
{% endapi-method-parameter %}

{% api-method-parameter name="accommodationId" type="integer" required=false %}
The unique accommodation id of related error report \(Required for accommodation group error\)
{% endapi-method-parameter %}

{% api-method-parameter name="roomReservationId" type="integer" required=false %}
The unique room reservation id of related error report \(Required for room reservation error\)
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "success": true,
  "id": 755
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

### Add Error Report _\(Related to Venue Booking\)_

```javascript
{
  "refType": 1,
  "code": "254856",
  "message": "This is an error reported while booking",
  "level": 3,
  "venueId": 107,
  "bookingId": 2256
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the error report was added to the account |
| id | The unique id of the error report |

## RefType

One of the following value:

| Type | refType |
| :--- | :--- |
| Custom | 0 |
| Venue Booking | 1 |
| Accommodation Group | 2 |
| Room Reservation | 3 |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24263 | The error report details are invalid. |
| Specific Code: 24264 | Detailed described error |



