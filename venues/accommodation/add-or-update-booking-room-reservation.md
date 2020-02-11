# Add or Update Booking Room Reservation

{% api-method method="post" host="\[PlatformAddress\]" path=" /api/1.0/venue?action=addOrUpdateBookingRoomReservation" %}
{% api-method-summary %}
Add or Update Booking Room Reservation
{% endapi-method-summary %}

{% api-method-description %}
Adds or updates the details of a specific room reservation on a specific venue booking. The booking must satisfy the following:\* Accommodation is included, and the booking has accommodation groups.\* The status must be "not confirmed", "confirmed", "checked in" or "checked out"
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
A json object that represents the room reservation to add or update. See below for the data description.
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A successful response to an add or update operation.  
NOTE: The "rooms" in the response are returned in the same order as the "rooms" in the request.
{% endapi-method-response-example-description %}

```javascript
{
  "success": true,
  "id": 123,
  "reference": "45",
  "mainGuest": {
    "id": 101,
    "contactId": 43213
  },
  "rooms": [
    {
      "id": 4001,
      "guest": {
        "id": 101,
        "contactId": 43213
      },
      "additionalGuests": []
    },
    {
      "id": 4002,
      "guest": {
        "id": 102,
        "contactId": 44321
      },
      "additionalGuests": [
        {
          "guestId": 103,
          "contactId": 43277,
          "guestType": 2
        }
      ]
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid request data that prevents the room reservation from being added/updated.
{% endapi-method-response-example-description %}

```javascript
{
  "errorCode": 400,
  "message": "The request contains invalid data",
  "specificCode": 24257,
  "additionalMessages": [
      "firstName: Value is required and can't be empty"
  ],
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Booking Room Reservation

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the room reservation to update - a new room reservation will be created if this parameter is not present |
| venueId | integer | required | The unique id of the venue to which the booking belongs |
| bookingId | integer | required | The unique id of the booking to which the room reservation belongs |
| canBeEdited | boolean | optional | Whether or not updates to the booking room reservation are allowed |
| mainGuest | [Guest](add-or-update-booking-room-reservation.md#guest) | required on add, optional on update | Details of the main guest of the room reservation |
| rooms | array of [Reserved Rooms](add-or-update-booking-room-reservation.md#reserved-room) | required on add, optional on update | Details of the individually reserved rooms on the reservation |
| removeRooms | array of integers | optional | The unique id of the individual rooms to remove from an existing reservation |

## Reserved Room

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the individual reserved room on the reservation to update. Omit this to create a new room on the reservation |
| guest | [Guest](add-or-update-booking-room-reservation.md#guest) | required on add, optional on update | Details of the guest on the individual reservation room |
| groupId | integer | required on add, optional on update | The unique id of the [accommodation group](add-or-update-booking-accommodation.md#booking-accommodation-group) from which the room is reserved |
| arrivalDate | date | required on add, optional on update | The arrival date of the reserved room |
| departureDate | date | required on add, optional on update | The departure date of the reserved room |
| excludedTaxIds | array of integers | optional | The unique ids of the taxes that are excluded from the daily rates |
| numAdultGuests | integer | required on add, optional on update | The number of adults on the reserved room. The value cannot exceed 10 |
| numChildGuests | integer | required on add, optional on update | The number of children on the reserved room. The value cannot exceed 10 |
| dayRates | array of [Day Rates](add-or-update-booking-room-reservation.md#reserved-room-day-rates) | required on add, optional on update | The daily rates of the reserved room |
| additionalGuests | array of [Additional  Guests](add-or-update-booking-room-reservation.md#reserved-room-additional-guests) | optional | The additional guests of the reserved room |
| overrideBlockCapacity | boolean | optional | Whether or not the reservations can exceed the block capacity |

## Reserved Room Day Rates

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| dayDate | date | required | The date of the reserved room to which the rate applies |
| cost | number | required | The rate amount for the reserved room on dayDate. The amount either includes or excludes tax depending on how the venue is configured |

## Reserved Room Additional Guests

| Property | Type | Required | Description |  |
| :--- | :--- | :--- | :--- | :--- |
| guestId | integer | required when **guest** is not set | The identifier of guest being updated on the reserved room |  |
| guest | [Guest](add-or-update-booking-room-reservation.md#guest) | required when **guestId** is not set | The additional guest details for the reserved room |  |
| arrivalDate | date | optional | The arrival date of the additional guest |  |
| departureDate | date | optional | The departure date of the additional guest |  |
| guestType | enum | optional \(required for **new** guests\) | The sharing type of additional guest. See [Additional Guest Type](add-or-update-booking-room-reservation.md#additional-guest-type) |  |

## Guest

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the venue guest to update |
| contact | [Contact](add-or-update-booking-room-reservation.md#guest-contact-details) | required on add, optional on update | The contact details of the guest |
| primaryPhone | string | optional | The primary phone number of the guest |
| address | [Address](../../development-reference/address-format.md) | optional | The address of the guest |

## Guest Contact Details

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| firstName | string | required | The first name of the contact |
| lastName | string | required | The last name of the contact |
| email | string | required | The email address of the contact |
| phone | string | optional | The mobile phone number of the contact |
| groups | array | optional | This is an array of group objects with the ‘groupId’ key. |

## Additional Guest Type

One of the following values

| \# | Description |
| :--- | :--- |
| 1 | Sharer |
| 2 | Accompanying |

## Notes on adding a room reservation

This action only supports adding a "not confirmed" room reservation. To add a "confirmed" room reservation, you will need to call the [confirmBookingRoomReservation](confirm-booking-room-reservation.md#confirm-booking-room-reservation) action after a successfull add.

This action only supports adding a room reservation to a booking that has [accommodation groups](add-or-update-booking-accommodation.md#booking-accommodation-group). The [rooms](add-or-update-booking-room-reservation.md#reserved-room) on the reservation must be assigned to a group.

## Notes on updating a room reservation

Updating an existing room reservation **overlays** the existing data. Optional request data that is excluded will not change existing data \(with the exception of _additionalGuests_ - see below\). This does not guarantee that the request data will validate if other data is changed. For example, if the departure date of a reserved room is extended, rates for the **new** dates will be required.

The following is an example of an update request that updates an existing room \(_id_ 400\) and adds a new room:

```javascript
"rooms": [
  {
    "id": 400,
    "arrivalDate": "2019-01-01",
    "departureDate": "2019-02-03",
    "dayRates": [
      {
        "dayDate": "2019-01-01",
        "cost": 100
      },
      {
        "dayDate": "2019-01-02",
        "cost": 101
      }
    ]
  },
  {
    "guest": {
      "id": 301
    },
    "groupId": 1,
    "arrivalDate": "2019-01-01",
    "departureDate": "2019-02-03",
    "numAdultGuests": 1,
    "numChildGuests": 0,
    "dayRates": [
      {
        "dayDate": "2019-01-01",
        "cost": 100
      },
      {
        "dayDate": "2019-01-02",
        "cost": 101
      }
    ]
]
```

Existing rooms can be **removed** from a reservation by passing their unique identifier in the _removeRooms_ of the request. Rooms are removed before other rooms in the request are added/updated.

### Updating additional guests on a reserved room

The _additionalGuests_ request param can be used to set the additional guest details of a reserved room. If this value is present in the request, it will become the **new** list of additional guests on the room. Therefore if you do **not** want to remove an additional guest, it must be present \(at least the _guestId_ value\) in the array.

If the value is **not** present in the request, the existing list of additional guests will remain. The details of the additional guests will still be validated against the updated reservation details. For example, if the _arrivalDate_ of the reserved rooms is updated, the new value will be validated against the existing additional guests. If the _arrivalDate_ of an existing additional guest is invalid, the request will be rejected.

## Notes on guest details in the request

Guests are **uniquely** identified based on the following \(in order\):  
1\) The unique _id_ value of the guest.  
2\) The combination of the guest's _email_, _firstName_, and _lastName_ \(case insensitive\).

Consider the following [guest](add-or-update-booking-room-reservation.md#guest) objects:

```javascript
{
  "id": 101,
  "primaryPhone": "123456789"
}

{
  "contact": {
    "firstName": "John",
    "lastName": "Doe",
    "email": "john.doe@somewhere.com",
    "groups": [{"groupId": 10}],
  },
  "primaryPhone": "0419111222"
}
```

The first object will update the guest with the unique id _101_. The request will fail if the guest does not exist. Only the _primaryPhone_ of the guest will be updated.

The second object will either create a new guest or update an existing one. If a guest already exists with the _firstName_ "John", _lastName_ "Doe", and _email_ "john.doe@somewhere.com" then that guest will be updated \(only the _primaryPhone_ of the guest will be updated\). Otherwise a new guest will be created.

If the same guest details appear multiple times in the request, only the details of the **first** guest are applied. For example, consider the following request data \(some details are omitted for simplicity\):

```javascript
{
  "venueId": 13,
  "bookingId": 1413,
  "mainGuest": {
    "contact": {
      "firstName": "John",
      "lastName": "Doe",
      "email": "John.Doe@somewhere.com",
      "phone": "12345678",
      "groups": [{"groupId": 10}],
    },
    "primaryPhone": "12345678"
  },
  "rooms": [
    {
      "guest": {
        "contact": {
          "firstName": "John",
          "lastName": "Doe",
          "email": "John.Doe@somewhere.com",
          "phone": "87654321",
          "groups": [{"groupId": 10}],
        },
        "primaryPhone": "87654321"
      },
      "groupId": 54,
      "arrivalDate": "2019-01-01",
      "departureDate": "2019-01-04"
    },
    {
      "guest": {
        "contact": {
          "firstName": "Jane",
          "lastName": "Doe",
          "email": "Jane.Doe@somewhere.com",
          "phone": "123123123",
          "groups": [{"groupId": 10}],
        },
        "primaryPhone": "123123123"
      },
      "groupId": 55,
      "arrivalDate": "2019-01-01",
      "departureDate": "2019-01-04"
    }
  ]
}
```

There are 2 **unique** guests in the above request data: John Doe, and Jane Doe. John Doe appears in the request twice \(first as _mainGuest_ and second as the _guest_ on the first room\). The details of the first appearance will be used when updating John Doe, therefore the _primaryPhone_ value will be "12345678", not "87654321".

