# Update Room Reservation Guest Contact

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="venue?action=updateBookingRoomReservationGuestContact" %}
{% api-method-summary %}
Update Room Reservation Guest Contact
{% endapi-method-summary %}

{% api-method-description %}
Updates the details of a venue booking room reservetion guest contact. It will only allow api callers to update a guest contact details. The only way new guests can be created is with addOrUpdateBookingRoomReservation API. NOTE: The venue must have access to update venue guest in order to call this api action.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the room reservetion guest contact to update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an update operation.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 8821,
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid request data that prevents the guest contact from being updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 400,
  "message": "The request contains invalid data",
  "specificCode": 24424,
  "additionalMessages": [
      "firstName: *Value is required and can't be empty*"
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Something unexpected occurred whilst processing the request. The guest contact should not be expected to be updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 500,
  "message": "An error has occurred",
  "specificCode": 24423,
  "additionalMessages": []
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Guest Contact

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the guest contact to update. |
| firstName | string | required | The first name of the guest contact. |
| lastName | string | required | The last name of the guest contact. |
| phone | string | required | The phone number of the guest contact. |
| email | string | required | The email address of the guest contact. |

## Update
When id is provided, it will fetch guest contact by id and update contact details.
when id parameter is missing, it will update guest contact based on firstName, lastName and email.

Note: You can not update guest contact which is anonymised.

## Example Request

```javascript
{
    "id": 12,
    "firstName": "First Name",
    "lastName": "Last Name",
    "phone": "123456",
    "email" : "test@email.com",
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the guest contact was updated |
| id | The unique id of the guest contact that was updated |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24421 | Could not find contact |
| Specific Code: 24422 | contact id or identity must be there |
| Specific Code: 24423 | An error has occurred |
| Specific Code: 24424 | The request contains invalid data |
| Specific Code: 24425 | The request contains invalid data |

