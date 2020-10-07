# Add or Update Booking

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/venue?action=addOrUpdateBooking" %}
{% api-method-summary %}
Add or Update Booking
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a venue booking.
NOTE: The venue must have access to _normal bookings_ in order to call this api action.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the booking to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation. NOTE: Additional warnings may be present to indicate issues that can occur when adding a new booking. See below for the description of these warnings.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 1234,
  "warnings": ["packageErrors", "packageSessionErrors"]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid request data that prevents the booking from being added/updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 400,
  "message": "The request contains invalid data",
  "specificCode": 24297,
  "additionalMessages": [
    "dateEventEnd: End date has to be greater than the start date."
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=429 %}
{% api-method-response-example-description %}
Too many requests to update the same booking.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 429
  "message": "Race condition error",
  "specificCode": 24299,
  "additionalMessages": []
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Something unexpected occurred whilst processing the request. The booking should not be expected to be added/updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 500,
  "message": "An error has occurred",
  "specificCode": 24296,
  "additionalMessages": []
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Booking

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the booking to update. A new booking will be created if this parameter is not present. |
| venueId | integer | required | The unique id of the venue to which the booking belongs. |
| leadId | integer | optional | The unique id of the opportunity to which the new booking will be assigned. Has no effect when updating a booking \(i.e. an existing booking cannot be assigned to another opportunity\). |
| bookingType | [Booking Type](add-or-update-booking.md#booking-type) | optional | The type of booking. Required when adding a new booking. Has no effect when updating a booking \(i.e the type of an existing booking cannot be changed\). |
| currentStatus | [Booking Status](add-or-update-booking.md#booking-status) | optional | The current status of the booking. Required when adding a new booking. Has no effect when updating a booking \(i.e. the status of an existing booking cannot be changed\). For example, to add a quote, the value should be 1. |
| code | string | optional | The unique reference code of the booking. Excluding this parameter from the request when adding a booking will cause the system to generate the code. The venue can be configured to prevent the code of an existing booking from being changed. |
| name | string | optional | The booking name. Required when adding a new booking. |
| companyId | integer | optional | The unique id of the company to assign to the booking. See [assigning a company/contact to the booking](add-or-update-booking.md#assigning-a-company-contact-to-the-booking). |
| company | object | optional | The data array of company. See addOrUpdateCompany API in contact namespace for parameters. |
| contactId | integer | optional | The unique id of the contact to assign to the booking See [assigning a company/contact to the booking](add-or-update-booking.md#assigning-a-company-contact-to-the-booking). |
| contact | object | optional | The data array of contact. See addOrUpdateContact API in contact namespace for parameters. |
| industryId | integer | optional | The unique id of the industry to which the _contact_ belongs when a _contact_ is [assigned to the booking](add-or-update-booking.md#assigning-a-company-contact-to-the-booking). |
| purchaseOrderNumber | string | optional | The purchase order number of the booking. |
| eventTypeId | integer | optional | The unique id of the booking event type. Required when adding a booking. |
| bookedById | integer | optional | The unique id of the account user who is the coordinator of the booking. Required when adding a new booking. |
| canBeMoved | boolean | optional | Whether or not the dates of the booking are flexible, and the booking itself can be moved to other dates. |
| dateEventStart | date | optional | The event start date of the booking. Required when adding a booking that includes event details. Has no effect if the venue doesn't have function space. |
| dateEventEnd | date | optional | The event end date of the booking. Required when adding a booking that includes event details. Has no effect if the venue doesn't have function space. When [adding a booking with an event template](add-or-update-booking.md#adding-an-event-template-to-a-new-booking), the end date cannot be more than 7 days after _dateEventStart_. |
| totalAttendees | integer | optional | The booking number of attendees. Required when adding a new booking. Has no effect when updating a booking \(i.e. the number of attendees on a booking cannot be changed\). When [adding a booking with an event template](add-or-update-booking.md#adding-an-event-template-to-a-new-booking), this number is assigned to the event template added to the booking. |
| packageId | integer | optional | The unique id of the event template that will be added to all event days \(i.e. dateEventStart to dateEventEnd\) of the _new_ booking. Has no effect when updating a booking \(i.e. this cannot be used to change the event templates on a booking\). See [adding an event template to a new booking](add-or-update-booking.md#adding-an-event-template-to-a-new-booking). |
| packagePrice | float | optional | The price of the event template added to the new booking. Has no effect when updating a booking. Excluding this parameter from the request will cause the system to use the price assigned to the event template by the venue. The value is rounded to 3 decimal places. |
| isAccommIncluded | boolean | optional | Whether or not the booking includes accommodation. Has no effect if the venue doesn't have accommodation. Always true for _accommodation only_ bookings. |
| dateAccomStart | date | optional | The earliest arrival date of the accommodation blocks on the booking. Required when adding a booking that includes accommodation. Has no effect if the venue doesn't have accommodation. |
| dateAccomEnd | date | optional | The latest departure date of the accommodation blocks on the booking. Required when adding a booking that includes accommodation. Has no effect if the venue doesn't have accommodation. |
| accommCutOffDate | date | optional | The cut off date for changes to the accommodation blocks on the booking. Only applies when the booking includes accommodation. |
| accommCancellationDate | date | optional | The date before which the accommodation blocks on the booking can be cancelled. Only applies when the booking includes accommodation. |
| accommChargingMethod | [Charging Method](add-or-update-booking.md#accommodation-charging-methods) | optional | The method used to charge for the accommodation blocks on the booking. Only applies when the booking includes accommodation. |
| accommGuaranteeRequired | boolean | optional | Whether or not a guarantee is required for the accommodation blocks on the booking. Only applies when the booking includes accommodation. |
| accommExternalBlockId | string | optional | The block id from an external pms \(property management system\). Only applies when the booking includes accommodation. |
| accommReservationMethod | [Reservation Method](add-or-update-booking.md#accommodation-reservation-methods) | optional | The method by which attendees will reserve rooms from the accommodation blocks on the booking. Only applies when the booking includes accommodation. |
| accommReservationCancellationDate | date | optional | The date after which reservations from the accommodation blocks cannot be cancelled. Only applies when the booking includes accommodation. |
| accommArrivalMethod | [Arrival Method](add-or-update-booking.md#accommodation-arrival-methods) | optional | The method by which the group attendees will arrive at the venue. Only applies when the booking includes accommodation. |
| isConfidential | boolean | optional | Whether or not the booking is confidential. Only applies when the venue's account has access to confidential meetings. |
| otaFolioRef | string | optional | The Folio ID from the external postings extension installed by the venue. |
| bookingRoleUserId1 | string | optional | The unique id of the account user assigned to the booking role label 1 |
| bookingRoleUserId2 | string | optional | The unique id of the account user assigned to the booking role label 2 |
| bookingRoleUserId3 | string | optional | The unique id of the account user assigned to the booking role label 3 |
| bookingRoleUserId4 | string | optional | The unique id of the account user assigned to the booking role label 4 |
| bookingRoleUserId5 | string | optional | The unique id of the account user assigned to the booking role label 5 |
| customFields | array of [Custom Field](add-or-update-booking.md#custom-field) | optional | The custom field values of the booking. A custom field value might be required depending on how it has been configured in the venue's account. |
| discountCode | string | optional | The discount code applied to the booking |

## Booking Type

The following booking types are supported when adding a new booking.

| Value | Description |
| :--- | :--- |
| 1 | A detailed booking that can include both event templates, and accommodation. Available only when the venue has function space. |
| 4 | A booking that only has accommodation. Available only when the venue has accommodation. |

## Booking Status

The following booking status options are supported when adding a new booking.

| Value | Description |
| :--- | :--- |
| 1 | Prospective |
| 2 | Tentative |
| 3 | Confirmed |
| 5 | Ordering |

## Accommodation Charging Methods

The following lists the accommodation charging method options.

| Value | Description |
| :--- | :--- |
| 0 | None |
| 1 | Individual Pays Own |
| 2 | Bill to Master |
| 3 | Combined |
| 4 | Complimentary |

## Accommodation Reservation Methods

The following lists the accommodation reservation method options.

| Value | Description |
| :--- | :--- |
| 1 | Rooming List |
| 2 | Individual Call-In |
| 3 | Booking Engine |
| 4 | Housing Form |

## Accommodation Arrival Methods

The following lists the accommodation arrival method options.

| Value | Description |
| :--- | :--- |
| 1 | Together |
| 2 | Individually |

## Custom Field

A booking custom field is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| fieldId | integer | required | The unique id of the booking custom field |
| fieldValue | mixed | required | The value of the booking custom field. Depends on the type of custom field value. |

## Special Considerations

### Assigning a company/contact to the booking

The _contact type_ of a booking is either a _company_ **or** a _contact_. When _companyId_ **or** _company_ is present in the request then the _contact type_ of the booking is set to _company_, and the _contactId_ **or** _contact_ must be a contact that belongs to that company. Otherwise the _contact type_ of the booking is set to _contact_ and contactId can be any valid contact in the venue's account.

If _contact_ and _company_ are present in request then it will link given contact to company.

A quote \(i.e. booking status is _prospective_\) that is assigned to an opportunity is forced to have the same _companyId_ and _contactId_ of the opportunity. Trying to change these values to something else will have no effect when updating the quote.

### Adding an event template to a new booking

Setting _packageId_ in the request when adding a _new_ booking will attempt to add that event template to _all_ event days of the booking _after_ the booking is created. There is no guarantee that the event template will be successfully added to all days of the booking. When the event template cannot be added to the booking, one or more [warnings](add-or-update-booking.md#response-warnings) will be returned in the response.

There are also the following additional restrictions:

* An event template can only be added when the venue has function spaces.
* An event template can only be added to a [detailed](add-or-update-booking.md#booking-type) booking.
* The maximum number of event days when adding an event template is 7.
* _packagePrice_ will be rounded to 3 decimal places if present in the request.

### Updating a booking

Updating a booking \(i.e. by setting _id_ in the request\) is an overlay action. This means the request can include only the details of the booking to be changed. This does not necessarily mean the operation will succeed. For example, the request might include the _dateEventEnd_ value, and not the _dateEventStart_ value. This scenario will fail if the value of _dateEventEnd_ is earlier than the current _dateEventStart_ value of the booking.

## Response Warnings

| Value | Description |
| :--- | :--- |
| packageErrors | The way the venue has configured the event template prevents it from being added to one or more event days of the booking. |
| packageSessionErrors | One or more sessions of the event template could not be added to the booking. This is usually caused by conflicting reservations on function space. |

## Unsupported Features

The following features are currently not supported by this api action:

* Recurring bookings
* _Simple_ booking types
* Discount settings
* Commission settings
* Multi language content

