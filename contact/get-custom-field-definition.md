# Get Custom Field Definition

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/contact?action=getCustomFieldDefinition" path="" %}
{% api-method-summary %}
Get Custom Field Definition
{% endapi-method-summary %}

{% api-method-description %}
Get the definition of custom field
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Returns

An array of objects with the following properties

| Property | Description |
| --- | --- |
| fieldId | The unique identifier for this custom field |
| fieldType | [The type of this field](get-custom-field-definition.md#types-of-field) |
| displayName | The name of this field |
| isRequired | If this field is required or not |
| sortOrder | Order to display this field |
| selectValues | Values that can be selected with select fields |
| fileTypes | Types of files that can be uploaded with the file custom field |

## Types of field

* 0 = Small Text
* 1 = Large Text
* 2 = Single Select
  * Valid options are provided in the ‘selectValues’ key
* 3 = Multiple Select
  * Valid options are provided in the ‘selectValues’ key
* 4 = Address
* 5 = Date
* 6 = File
  * Valid file types are provided in the ‘fileTypes’ key
* 7 = Static Text
  * Values cannot be set for this type
* 8 = Whole Number

This call will return an array of custom fields available on the account. The result will have the fieldId which is the unique field identifier for the specific field, as well as the display name and any options required for each field.

As part of the field definition there is a ‘fieldType’ property which can be resolved to the following types

* 0 = Small Text
* 1 = Large Text
* 2 = Single Select
  * Valid options are provided in the ‘selectValues’ key
* 3 = Multiple Select
  * Valid options are provided in the ‘selectValues’ key
* 4 = Address
* 5 = Date
* 6 = File
  * Valid file types are provided in the ‘fileTypes’ key
* 7 = Static Text
  * Values cannot be set for this type
* 8 = Whole Number

