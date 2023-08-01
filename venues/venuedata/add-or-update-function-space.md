# Add or Update Function Space

## Add or Update Function Space

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=addOrUpdateFunctionSpace" method="post" summary="Add or Update Function Space" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the function space to update (Leave empty if adding a new space )
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the function space belongs
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name of the function space (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="description" type="string" in="path" %}
The description of the function space
{% endswagger-parameter %}

{% swagger-parameter name="categoryId" type="integer" in="path" %}
The categoryId id of the function space
{% endswagger-parameter %}

{% swagger-parameter name="hasLayouts" type="boolean" in="path" %}
Whether or not the function space has layout
{% endswagger-parameter %}

{% swagger-parameter name="minPax" type="integer" in="path" %}
The minimum pax of the function space (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="maxPax" type="integer" in="path" %}
The maximum pax of the function space (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="maxNumBookings" type="integer" in="path" %}
The maximum number bookings of the function space (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="area" type="integer" in="path" %}
The usable floor area of the function space
{% endswagger-parameter %}

{% swagger-parameter name="length" type="integer" in="path" %}
The usable length of the function space
{% endswagger-parameter %}

{% swagger-parameter name="width" type="integer" in="path" %}
The usable width of the function space
{% endswagger-parameter %}

{% swagger-parameter name="heightMaximum" type="integer" in="path" %}
The usable width of the function space
{% endswagger-parameter %}

{% swagger-parameter name="heightMinimum" type="integer" in="path" %}
The mminimum height of the function space
{% endswagger-parameter %}

{% swagger-parameter name="floorPressureMaximum" type="integer" in="path" %}
The maximum floor pressure allowed for the function space
{% endswagger-parameter %}

{% swagger-parameter name="isViewable" type="boolean" in="path" %}
Whether or not the function space is viewable on marketplace (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="eventTypes" type="array" in="path" %}
The event type ids applied to the function space
{% endswagger-parameter %}

{% swagger-parameter name="marketplaceName" type="string" in="path" %}
The name of the space displayed in marketplace and booking engines
{% endswagger-parameter %}

{% swagger-parameter name="hasSmallerSpaces" type="boolean" in="path" %}
Whether or not this space can be divided into smaller, individual spaces (Required when the ID parameter is missing)
{% endswagger-parameter %}

{% swagger-parameter name="partSpaceIds" type="array" in="path" %}
The smallest individual spaces that are available within this space. Also include the smallest spaces that overlap other spaces (Only used when hasSmallerSpaces=true)
{% endswagger-parameter %}

{% swagger-parameter name="includedInReportDashboard" type="boolean" in="path" %}
Whether or not this space should be included in the reporting dashboard calculations (e.g. CI revenue per function space)
{% endswagger-parameter %}

{% swagger-parameter name="threeDScanId" type="string" in="path" %}
The 3D scan ID which will show 3D view of your space on iVvy
{% endswagger-parameter %}

{% swagger-parameter name="useIntegrationPartner" type="boolean" in="path" %}
Whether this function space is integrated with ResDiary
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

| Property | Description                                         |
| -------- | --------------------------------------------------- |
| success  | Whether or not the function space was added/updated |
| id       | The unique id of the function space                 |

### Throws

| Code                 | Description                       |
| -------------------- | --------------------------------- |
| Specific Code: 24385 | The function space does not exist |
| Specific Code: 24386 | An unknown error has occurred     |
| Specific Code: 24387 | The request contains invalid data |
| Specific Code: 24388 | The request contains invalid data |
