# Get Booking Custom Field List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getBookingCustomFieldList" path="" %}
{% api-method-summary %}
Get Booking Custom Field List
{% endapi-method-summary %}

{% api-method-description %}
Return the booking custom fields (definition) list.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}

{% api-method-parameter name="perPage" type="integer" required=false %}
The number of booking custom fields to get in a single call
{% endapi-method-parameter %}

{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 9,
        "start": 0,
        "perPage": 100,
        "count": 9
    },
    "results": [
        {
            "id": 1,
            "fieldType": 0,
            "displayName": "Small Text",
            "isRequired": false,
            "visibleTo": 3,
            "userGroupIds": [
                10
            ],
            "tooltipText": "",
            "isRequiredOnMarketplace": false,
            "sortOrder": 0,
            "selectValues": null
        },
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get Venues Function Space Category List`

```javascript
{
    "perPage":10
}
```

## Returns

`A collection object with the following properties in the results`

| Property | Data Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the booking custom field. |
| fieldType | integer | The [type](get-booking-custom-field-list.md#type) of this field. |
| displayName | string | The name of this field. |
| isRequired | boolean | If this is a required field. |
| visibleTo | integer | Field [visiblity options](get-booking-custom-field-list.md#visiblity-to-options).|
| userGroupIds | array | Ids of user groups if visible to specific user groups. |
| tooltipText | string | Tooltip text of the custom field. |
| isRequiredOnMarketplace | boolean | Whether or not the field is required on marketplace. |
| sortOrder | integer | Order to display this field. |
| selectValues | object | Values that can be selected with select fields. |

## Type

| #  | Description         |
| -- | ------------------- |
| 0  | Small Text             |
| 1  | Large Text         |
| 2  | Single Select      |
| 3  | Multi Select              |
| 5  | Date              |
| 10  | Html Text               |

## Visiblity to Options

| #  | Description         |
| -- | ------------------- |
| 1  | All             |
| 2  | User Group             |
| 3  | None             |


### Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24150 | Account does not exist |