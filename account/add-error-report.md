# Add Error Report

**NOTE: This action has not been published**

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
The type of the error report e.g. booking, accommodation group..
{% endapi-method-parameter %}

{% api-method-parameter name="refId1" type="integer" required=false %}
The reference identifier 1 of the error report
{% endapi-method-parameter %}

{% api-method-parameter name="refId2" type="integer" required=false %}
The reference identifier 2 of the error report
{% endapi-method-parameter %}

{% api-method-parameter name="refId3" type="integer" required=false %}
The reference identifier 3 of the error report
{% endapi-method-parameter %}

{% api-method-parameter name="refId4" type="integer" required=false %}
The reference identifier 4 of the error report
{% endapi-method-parameter %}

{% api-method-parameter name="refId5" type="integer" required=false %}
The reference identifier 5 of the error report
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
  "refType": 2,
  "code": "254856",
  "message": "This is an error reported while booking",
  "level": 3,
  "refId1": 107,
  "refId2": 2256,
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
| Custom | 1 |
| Venue Booking | 2 |
| Accommodation Group | 3 |
| Room Reservation | 4 |

Pass refIds as per below mapping. All below mentioned refIds are mandatory to pass in order to save an error report against specific model.

## RefType-RefId Mapping

#### Venue Booking

| RefId | Related identifier |
| :--- | :--- |
| refId1 |  The identifier of venue |
| refId2 | The identifier of venue booking |

#### Accommodation Group

| RefId | Related identifier |
| :--- | :--- |
| refId1 |  The identifier of venue |
| refId2 | The identifier of venue booking |
| refId3 | The identifier of booking accommodation group |

#### Room Reservation

| RefId | Related identifier |
| :--- | :--- |
| refId1 | The identifier of venue |
| refId2 | The identifier of venue booking |
| refId3 | The identifier of room reservation |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24262 | The error report details are invalid. |
