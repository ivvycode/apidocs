# Add or Update Booking Session Resource

## Add or Update Booking Session Resource

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=addOrUpdateBookingSessionResource" method="post" summary="Add or Update Booking Session Resource" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the booking session resource belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="path" %}
The unique id of the booking to which the session resource belongs
{% endswagger-parameter %}

{% swagger-parameter name="sessionId" type="integer" in="path" %}
The unique id of the booking session to which the resource belongs
{% endswagger-parameter %}

{% swagger-parameter name="resourceId" type="integer" in="path" %}
The unique id of the session resource to which the booking session resource belongs
{% endswagger-parameter %}

{% swagger-parameter name="quantity" type="integer" in="path" %}
The quantity of the session resource (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="startTime" type="time" in="path" %}
The startTime of the session resource (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="endTime" type="time" in="path" %}
The endTime of the session resource (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="includeInPackage" type="boolean" in="path" %}
Whether or not the booking session resource is included in booking package (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="bookingPackageId" type="integer" in="path" %}
The booking package identifier if the booking session resource is included in package (Required when includeInPackage=1)
{% endswagger-parameter %}

{% swagger-parameter name="costCenterId" type="integer" in="path" %}
The cost center identifier to which the booking session resource's revenue applies (Required when includeInPackage=0)
{% endswagger-parameter %}

{% swagger-parameter name="cost" type="double" in="path" %}
The cost of the booking session resource (Required when includeInPackage=0)
{% endswagger-parameter %}

{% swagger-parameter name="costType" type="integer" in="path" %}
The cost type of the booking session resource Cost Type (Required when includeInPackage=0)
{% endswagger-parameter %}

{% swagger-parameter name="excludedTaxIds" type="array" in="path" %}
The excluded tax identifiers of the booking session resource (Only used when includeInPackage=0)
{% endswagger-parameter %}

{% swagger-parameter name="hasCommissions" type="boolean" in="path" %}
The booking session resource pay comissions to an agent
{% endswagger-parameter %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the booking session resource (Leave empty if adding a new booking session resource)
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true,
  "id": 7
}
```
{% endswagger-response %}
{% endswagger %}

## Cost Type

One of the following values:

* 1 = Hourly
* 2 = Daily

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
| -------- | ------------------------------------------------------------- |
| success  | Whether or not the booking session resource was added/updated |
| id       | The unique id of the booking session resource                 |

### Throws

| Code                 | Description                                 |
| -------------------- | ------------------------------------------- |
| Specific Code: 24338 | The booking session does not exist          |
| Specific Code: 24339 | The booking session resource does not exist |
| Specific Code: 24340 | An unknown error has occurred               |
| Specific Code: 24341 | The request contains invalid data           |
| Specific Code: 24342 | The request contains invalid data           |
