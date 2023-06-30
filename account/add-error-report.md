# Add Error Report

{% swagger baseUrl="[PlatformAddress]/api/1.0/account?action=addErrorReport" method="post" summary="Add Error Report" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="code" type="string" in="path" %}
The distinguish code of error report
{% endswagger-parameter %}

{% swagger-parameter name="message" type="string" in="path" %}
Th message description of an error report
{% endswagger-parameter %}

{% swagger-parameter name="level" type="integer" in="path" %}
The severity level of an error report
{% endswagger-parameter %}

{% swagger-parameter name="refType" type="integer" in="path" %}
The type of the error report e.g. booking, accommodation group..
{% endswagger-parameter %}

{% swagger-parameter name="refId1" type="integer" in="path" %}
The reference identifier 1 of the error report
{% endswagger-parameter %}

{% swagger-parameter name="refId2" type="integer" in="path" %}
The reference identifier 2 of the error report
{% endswagger-parameter %}

{% swagger-parameter name="refId3" type="integer" in="path" %}
The reference identifier 3 of the error report
{% endswagger-parameter %}

{% swagger-parameter name="refId4" type="integer" in="path" %}
The reference identifier 4 of the error report
{% endswagger-parameter %}

{% swagger-parameter name="refId5" type="integer" in="path" %}
The reference identifier 5 of the error report
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true,
  "id": 755
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

### Add Error Report _(Related to Venue Booking)_

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

| Property | Description                                              |
| -------- | -------------------------------------------------------- |
| success  | Whether or not the error report was added to the account |
| id       | The unique id of the error report                        |

## RefType

One of the following value:

| Type                | refType |
| ------------------- | ------- |
| Custom              | 1       |
| Venue Booking       | 2       |
| Accommodation Group | 3       |
| Room Reservation    | 4       |

Pass refIds as per below mapping. All below mentioned refIds are mandatory to pass in order to save an error report against specific model.

## RefType-RefId Mapping

#### Venue Booking

| RefId  | Related identifier              |
| ------ | ------------------------------- |
| refId1 | The identifier of venue         |
| refId2 | The identifier of venue booking |

#### Accommodation Group

| RefId  | Related identifier                            |
| ------ | --------------------------------------------- |
| refId1 | The identifier of venue                       |
| refId2 | The identifier of venue booking               |
| refId3 | The identifier of booking accommodation group |

#### Room Reservation

| RefId  | Related identifier                 |
| ------ | ---------------------------------- |
| refId1 | The identifier of venue            |
| refId2 | The identifier of venue booking    |
| refId3 | The identifier of room reservation |

## Throws

| Code                 | Description                           |
| -------------------- | ------------------------------------- |
| Specific Code: 24262 | The error report details are invalid. |
