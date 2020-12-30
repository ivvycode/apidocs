# Add or Update Function Space

## Add or Update Function Space

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=addOrUpdateFunctionSpace" path="" %}
{% api-method-summary %}
Add or Update Function Space
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}

{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the function space to update \(Leave empty if adding a new space \)
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the function space belongs
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
The name of the function space \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
The description of the function space
{% endapi-method-parameter %}

{% api-method-parameter name="categoryId" type="integer" required=false %}
The categoryId id of the function space
{% endapi-method-parameter %}

{% api-method-parameter name="hasLayouts" type="boolean" required=false %}
Whether or not the function space has layout
{% endapi-method-parameter %}

{% api-method-parameter name="minPax" type="integer" required=true %}
The minimum pax of the function space \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="maxPax" type="integer" required=true %}
The maximum pax of the function space \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="maxNumBookings" type="integer" required=true %}
The maximum number bookings of the function space \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="area" type="integer" required=false %}
The usable floor area of the function space
{% endapi-method-parameter %}

{% api-method-parameter name="length" type="integer" required=false %}
The usable length of the function space
{% endapi-method-parameter %}

{% api-method-parameter name="width" type="integer" required=false %}
The usable width of the function space
{% endapi-method-parameter %}

{% api-method-parameter name="heightMaximum" type="integer" required=false %}
The usable width of the function space
{% endapi-method-parameter %}

{% api-method-parameter name="heightMinimum" type="integer" required=false %}
The mminimum height of the function space
{% endapi-method-parameter %}

{% api-method-parameter name="floorPressureMaximum" type="integer" required=false %}
The maximum floor pressure allowed for the function space
{% endapi-method-parameter %}

{% api-method-parameter name="isViewable" type="boolean" required=true %}
Whether or not the function space is viewable on marketplace \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="eventTypes" type="array" required=false %}
The event type ids applied to the function space
{% endapi-method-parameter %}

{% api-method-parameter name="marketplaceName" type="string" required=false %}
The name of the space displayed in marketplace and booking engines
{% endapi-method-parameter %}

{% api-method-parameter name="hasSmallerSpaces" type="boolean" required=true %}
Whether or not this space can be divided into smaller, individual spaces \(Required when the ID parameter is missing\)
{% endapi-method-parameter %}

{% api-method-parameter name="partSpaceIds" type="array" required=true %}
The smallest individual spaces that are available within this space. Also include the smallest spaces that overlap other spaces \(Only used when hasSmallerSpaces=true\)
{% endapi-method-parameter %}

{% api-method-parameter name="includedInReportDashboard" type="boolean" required=false %}
Whether or not this space should be included in the reporting dashboard calculations (e.g. CI revenue per function space)
{% endapi-method-parameter %}

{% api-method-parameter name="threeDScanId" type="string" required=false %}
The 3D scan ID which will show 3D view of your space on iVvy
{% endapi-method-parameter %}

{% api-method-parameter name="useIntegrationPartner" type="boolean" required=false %}
Whether this function space is integrated with ResDiary
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

### Example Request

#### Add function space

```javascript
{
    "venueId": 1,
    "name": "test",
    "minPax": 5,
    "maxPax": 0,
    "maxNumBookings": 50,
    "isViewable": false,
    "hasSmallerSpaces": false
}
```

#### Update function space

```javascript
{
    "id": 7,
    "venueId": 1,
    "name": "test",
    "minPax": 5,
    "maxPax": 0,
    "maxNumBookings": 50,
    "isViewable": false,
    "hasSmallerSpaces": false
}
```

### Returns

| Property | Description                                                   |
| :------- | :------------------------------------------------------------ |
| success  | Whether or not the function space was added/updated |
| id       | The unique id of the function space                 |

### Throws

| Code                 | Description                                 |
| :------------------- | :------------------------------------------ |
| Specific Code: 24385 | The function space does not exist           |
| Specific Code: 24386 | An unknown error has occurred               |
| Specific Code: 24387 | The request contains invalid data           |
| Specific Code: 24388 | The request contains invalid data           |
