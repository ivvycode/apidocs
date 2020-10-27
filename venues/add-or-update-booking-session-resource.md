# Add or Update Booking Session Resource

## Add or Update Booking Session Resource

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateBookingSessionResource" path="" %}
{% api-method-summary %}
Add or Update Booking Session Resource
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the booking session resource belongs
{% endapi-method-parameter %}

{% api-method-parameter name="bookingId" type="integer" required=true %}
The unique id of the booking to which the session resource belongs
{% endapi-method-parameter %}

{% api-method-parameter name="sessionId" type="integer" required=true %}
The unique id of the booking session to which the resource belongs
{% endapi-method-parameter %}

{% api-method-parameter name="resourceId" type="integer" required=true %}
The unique id of the session resource to which the booking session resource belongs
{% endapi-method-parameter %}

{% api-method-parameter name="quantity" type="integer" required=true %}
The quantity of the session resource \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="quantity" type="integer" required=true %}
The quantity of the session resource \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="startTime" type="time" required=true %}
The startTime of the session resource \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="endTime" type="time" required=true %}
The endTime of the session resource \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="includeInPackage" type="boolean" required=true %}
Whether or not the booking session resource is included in booking package \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="bookingPackageId" type="integer" required=true %}
The booking package identifier if the booking session resource is included in package \(Required when includeInPackage=1\)
{% endapi-method-parameter %}

{% api-method-parameter name="costCenterId" type="integer" required=true %}
The cost center identifier to which the booking session resource's revenue applies \(Required when includeInPackage=0\)
{% endapi-method-parameter %}

{% api-method-parameter name="cost" type="double" required=true %}
The cost of the booking session resource \(Required when includeInPackage=0\)
{% endapi-method-parameter %}

{% api-method-parameter name="costType" type="integer" required=true %}
The cost type of the booking session resource [Cost Type](add-or-update-booking-session-resource.md#cost-type) \(Required when includeInPackage=0\)
{% endapi-method-parameter %}

{% api-method-parameter name="excludedTaxIds" type="array" required=false %}
The excluded tax identifiers of the booking session resource \(Only used when includeInPackage=0\)
{% endapi-method-parameter %}

{% api-method-parameter name="hasCommissions" type="boolean" required=false %}
The booking session resource pay comissions to an agent
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the booking session resource \(Leave empty if adding a new booking session resource\)
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
  "id": 7
}
```

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Cost Type

One of the following values:

- 1 = Hourly
- 2 = Daily

### Example Request

#### Add booking session resource

```javascript
{
    "venueId": 9,
    "bookingId": 29063,
    "sessionId": 19792,
    "resourceId": 27,
    "quantity": 10,
    "startTime": "5:00 AM",
    "endTime": "7:00 AM",
    "includeInPackage": 0,
    "bookingPackageId": 1,
    "cost": 25,
    "costType": 1,
    "costCenterId": 4
}
```

#### Update booking session resource

```javascript
{
  "id": 7,
  "venueId": 9,
  "bookingId": 29063,
  "sessionId": 19792,
  "startTime": "6:00 AM",
}
```

### Returns

| Property | Description                                                   |
| :------- | :------------------------------------------------------------ |
| success  | Whether or not the booking session resource was added/updated |
| id       | The unique id of the booking session resource                 |

### Throws

| Code                 | Description                                 |
| :------------------- | :------------------------------------------ |
| Specific Code: 24338 | The booking session does not exist          |
| Specific Code: 24339 | The booking session resource does not exist |
| Specific Code: 24340 | An unknown error has occurred               |
| Specific Code: 24341 | The request contains invalid data           |
| Specific Code: 24342 | The request contains invalid data           |
