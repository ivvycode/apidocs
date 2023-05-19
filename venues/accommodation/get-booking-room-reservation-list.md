# Get Booking Room Reservation List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getBookingRoomReservationList" method="post" summary="Get Booking Room Reservation List" %}
{% swagger-description %}
Get a list of booking room reservations for venue.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" %}
The unique id of the venue to which the bookings belong
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="body" %}
The unique id of the booking to which the room reservations belong
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="body" %}
The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.)
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="body" %}
The number of booking room reservations to fetch
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 5,
        "count": 1
    },
    "results": [{
        "id": 3241,
        "venueId": 131,
        "bookingId": 4248,
        "reference": 164,
        "mainGuestId": 542,
        "mainGuest": {
            "id": 542,
            "contact": {
                "id": 431,
                "firstName": "Test1",
                "lastName": "Com1",
                "email": "test1.com1@somewhere.com",
                "phone": "071234567890",
                "createdDate": "2018-08-17 14:51:35 UTC",
                "modifiedDate": "2018-08-17 14:51:35 UTC"
            },
            "guestContact": {
                "id": 431,
                "firstName": "Test1",
                "lastName": "Com1",
                "email": "test1.com1@somewhere.com",
                "phone": "071234567890",
                "createdDate": "2018-08-17 14:51:35 UTC",
                "modifiedDate": "2018-08-17 14:51:35 UTC"
            },
            "primaryPhone": "071234567890",
            "address": null,
            "createdDate": "2018-08-17 14:51:35 UTC",
            "modifiedDate": "2018-08-17 14:51:35 UTC"
        },
        "currentStatus": 2,
        "isFromGroup": true,
        "totalAmount": 745.00,
        "rooms": [
            {
                "id": 123,
                "guestId": 542,
                "guest": {
                    "id": 542,
                    "contact": {
                        "id": 431,
                        "firstName": "Test1",
                        "lastName": "Com1",
                        "email": "test1.com1@somewhere.com",
                        "phone": "071234567890",
                        "createdDate": "2018-08-17 14:51:35 UTC",
                        "modifiedDate": "2018-08-17 14:51:35 UTC"
                    },
                    "guestContact": {
                        "id": 431,
                        "firstName": "Test1",
                        "lastName": "Com1",
                        "email": "test1.com1@somewhere.com",
                        "phone": "071234567890",
                        "createdDate": "2018-08-17 14:51:35 UTC",
                        "modifiedDate": "2018-08-17 14:51:35 UTC"
                    },
                    "primaryPhone": "071234567890",
                    "address": null,
                    "createdDate": "2018-08-17 14:51:35 UTC",
                    "modifiedDate": "2018-08-17 14:51:35 UTC"
                },
                "barId": 57,
                "roomId": 14,
                "groupId": 7589,
                "currentStatus": 3,
                "numRooms": 1,
                "arrivalDate": "2018-09-01",
                "departureDate": "2018-09-04",
                "totalAmount": 545.00,
                "excludedTaxIds": [],
                "numAdultGuests": 1,
                "numChildGuests": 0,
                "createdDate": "2018-08-17 14:51:35 UTC",
                "modifiedDate": "2018-08-17 14:51:35 UTC",
                "isCancelled": false,
                "cancelledDate": null,
                "dayRates": [
                    {
                        "dayDate": "2018-09-01",
                        "barId": 57,
                        "cost": 180.00
                    },
                    {
                        "dayDate": "2018-09-02",
                        "barId": 57,
                        "cost": 190.00
                    },
                    {
                        "dayDate": "2018-09-03",
                        "barId": 57,
                        "cost": 175.00
                    }
                ],
                "additionalGuests": []
            },
            {
                "id": 124,
                "guestId": 543,
                "guest": {
                    "id": 543,
                    "contact": {
                        "id": 432,
                        "firstName": "Test2",
                        "lastName": "Com2",
                        "email": "test2.com2@somewhere.com",
                        "phone": "",
                        "createdDate": "2018-08-17 14:52:21 UTC",
                        "modifiedDate": "2018-08-17 14:52:21 UTC"
                    },
                    "guestContact": {
                        "id": 432,
                        "firstName": "Test2",
                        "lastName": "Com2",
                        "email": "test2.com2@somewhere.com",
                        "phone": "",
                        "createdDate": "2018-08-17 14:52:21 UTC",
                        "modifiedDate": "2018-08-17 14:52:21 UTC"
                    },
                    "primaryPhone": "070987654321",
                    "address": {
                        "line1": "123 Some Street",
                        "line2": "",
                        "line3": "",
                        "line4": "",
                        "city": "Brisbane",
                        "postalCode": "4001",
                        "countryCode": "AU",
                        "stateCode": "QLD",
                        "stateName": ""
                    },
                    "createdDate": "2018-08-17 14:52:21 UTC",
                    "modifiedDate": "2018-08-17 14:52:21 UTC"
                },
                "barId": 57,
                "roomId": 14,
                "groupId": 7589,
                "currentStatus": 3,
                "numRooms": 1,
                "arrivalDate": "2018-09-02",
                "departureDate": "2018-09-03",
                "totalAmount": 200.00,
                "excludedTaxIds": [],
                "numAdultGuests": 1,
                "numChildGuests": 0,
                "createdDate": "2018-08-17 14:52:21 UTC",
                "modifiedDate": "2018-08-17 14:52:21 UTC",
                "isCancelled": false,
                "cancelledDate": null,
                "dayRates": [
                    {
                        "date": "2018-09-02",
                        "barId": 57,
                        "cost": 200.00
                    }
                ],
                "additionalGuests": [
                    {
                        "guestId": 601,
                        "guest": {
                            "id": 601,
                            "contact": {
                                "id": 800,
                                "firstName": "Jane",
                                "lastName": "Doe",
                                "email": "Jane.Doe@test.com",
                                "phone": "123654789",
                                "createdDate": "2018-08-17 18:43:33 UTC",
                                "modifiedDate": "2018-08-17 18:43:33 UTC"
                            },
                            "guestContact": {
                                "id": 800,
                                "firstName": "Jane",
                                "lastName": "Doe",
                                "email": "Jane.Doe@test.com",
                                "phone": "123654789",
                                "createdDate": "2018-08-17 18:43:33 UTC",
                                "modifiedDate": "2018-08-17 18:43:33 UTC"
                            },
                            "primaryPhone": "123654789",
                            "address": null,
                            "createdDate": "2018-08-17 18:43:33 UTC",
                            "modifiedDate": "2018-08-17 18:43:33 UTC"
                        },
                        "arrivalDate": "2018-09-02",
                        "departureDate": "2018-09-03",
                        "guestType": 2
                    }
                ],
                "overrideBlockCapacity": true
            }
        ]
    }]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of booking room reservation records the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Booking Room Reservation

| Property      | Type                                                                          | Description                                                                                                                   |
| ------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| id            | integer                                                                       | The unique id of the booking room reservation                                                                                 |
| venueId       | integer                                                                       | The unique id of the venue to which the booking belongs                                                                       |
| bookingId     | integer                                                                       | The unique id of the booking to which the room reservation belongs                                                            |
| canBeEdited   | boolean                                                                       | Whether or not changes to the booking room reservation are allowed                                                            |
| reference     | integer                                                                       | A unique reference assigned to the room reservation                                                                           |
| mainGuestId   | integer                                                                       | The unique id of the main guest of the reservation                                                                            |
| mainGuest     | [Guest](get-booking-room-reservation-list.md#guest)                           | Details of the main guest of the room reservation                                                                             |
| currentStatus | integer                                                                       | The current [status](get-booking-room-reservation-list.md#room-reservation-status) of the room reservation                    |
| cancelledDate | datetime                                                                      | The date & time the room reservation was cancelled                                                                            |
| isFromGroup   | boolean                                                                       | Whether or not the room reservation applies to an [accommodation group](get-booking-accommodation-list.md)                    |
| totalAmount   | number                                                                        | The total amount of the room reservation. The amount either includes or excludes tax depending on how the venue is configured |
| createdDate   | datetime                                                                      | The date & time the room reservation was created                                                                              |
| modifiedDate  | datetime                                                                      | The date & time the room reservation was last modified                                                                        |
| rooms         | array of [Reserved Rooms](get-booking-room-reservation-list.md#reserved-room) | The details of the rooms that have been reserved                                                                              |

## Room Reservation Status

| Status | Description   |
| ------ | ------------- |
| 1      | Not confirmed |
| 2      | Confirmed     |
| 3      | Cancelled     |
| 4      | Checked In    |
| 5      | Checked Out   |

## Reserved Room

| Property              | Type                                                                                               | Description                                                                                                                                                                                                                        |
| --------------------- | -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                    | integer                                                                                            | The unique id of the reserved room                                                                                                                                                                                                 |
| guestId               | integer                                                                                            | The unique id of the venue guest                                                                                                                                                                                                   |
| guest                 | [Guest](get-booking-room-reservation-list.md#guest)                                                | Details of the guest assigned to the reserved room                                                                                                                                                                                 |
| barId                 | integer                                                                                            | The unique id of the rate plan assigned to the reserved room. If the reserved room applies to an accommodation group (see property _isFromGroup_ above) then this will always be the rate plan assigned to the accommodation group |
| roomId                | integer                                                                                            | The unique id of the room type that is reserved. If the reserved room applies to an accommodation group (see property _isFromGroup_ above) then this will always be the room type assigned to the accommodation group              |
| groupId               | integer                                                                                            | The unique id of the [accommodation group](get-booking-accommodation-list.md) from which the room is reserved (see property _isFromGroup_ above)                                                                                   |
| currentStatus         | integer                                                                                            | The current [status](get-booking-room-reservation-list.md#reserved-room-status) of the reserved room                                                                                                                               |
| numRooms              | integer                                                                                            | The number of rooms reserved. This value is always 1                                                                                                                                                                               |
| arrivalDate           | date                                                                                               | The arrival date of the reserved room                                                                                                                                                                                              |
| departureDate         | date                                                                                               | The departure date of the reserved room                                                                                                                                                                                            |
| totalAmount           | number                                                                                             | The total amount of the reserved room. The amount either includes or excludes tax depending on how the venue is configured                                                                                                         |
| excludedTaxIds        | array of integers                                                                                  | The unique ids of the taxes that are excluded from the daily rates                                                                                                                                                                 |
| numAdultGuests        | integer                                                                                            | The number of adults on the reserved room                                                                                                                                                                                          |
| numChildGuests        | integer                                                                                            | The number of children on the reserved room                                                                                                                                                                                        |
| createdDate           | datetime                                                                                           | The date & time the reserved room was created                                                                                                                                                                                      |
| modifiedDate          | datetime                                                                                           | The date & time the reserved room was last modified                                                                                                                                                                                |
| isCancelled           | boolean                                                                                            | Whether or not the reserved room is cancelled                                                                                                                                                                                      |
| cancelledDate         | datetime                                                                                           | The date & time the reserved room was cancelled                                                                                                                                                                                    |
| dayRates              | array of [Day Rates](get-booking-room-reservation-list.md#reserved-room-day-rates)                 | The daily rates of the reserved room                                                                                                                                                                                               |
| additionalGuests      | array of [Additional Guests](get-booking-room-reservation-list.md#reserved-room-additional-guests) | The additional guests of the reserved room                                                                                                                                                                                         |
| overrideBlockCapacity | boolean                                                                                            | Whether or not the number of reservations can exceed the block                                                                                                                                                                     |
| occType               | integer                                                                                            | The occupancy type of the reserverd room See [Occupancy Type](add-or-update-booking-room-reservation.md#occupancy-type)                                                                                                            |

## Reserved Room Status

| Status | Description   |
| ------ | ------------- |
| 1      | Not confirmed |
| 2      | Confirmed     |
| 3      | Cancelled     |
| 4      | Checked In    |
| 5      | Checked Out   |

## Reserved Room Day Rates

| Property | Type    | Description                                                                                                                                                                                                                                       |
| -------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dayDate  | date    | The date of the reserved room to which the rate applies                                                                                                                                                                                           |
| barId    | integer | The unique id of the rate plan assigned to the dayDate of the reserved room. If the reserved room applies to an accommodation group (see property _isFromGroup_ above) then this will always be the room type assigned to the accommodation group |
| cost     | number  | The rate amount for the reserved room on dayDate. The amount either includes or excludes tax depending on how the venue is configured                                                                                                             |

## Reserved Room Additional Guests

| Property      | Type                                                | Description                                                                                                                        |
| ------------- | --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| guestId       | integer                                             | The identifier of guest being updated on the reserved room                                                                         |
| guest         | [Guest](get-booking-room-reservation-list.md#guest) | The additional guest details for the reserved room                                                                                 |
| arrivalDate   | date                                                | The arrival date of the additional guest                                                                                           |
| departureDate | date                                                | The departure date of the additional guest                                                                                         |
| guestType     | enum                                                | The sharing type of additional guest. See [Additional Guest Type](add-or-update-booking-room-reservation.md#additional-guest-type) |

## Guest

| Property     | Type                                                                  | Description                                       |
| ------------ | --------------------------------------------------------------------- | ------------------------------------------------- |
| id           | integer                                                               | The unique id of the venue guest                  |
| guestContact      | [Contact](get-booking-room-reservation-list.md#guest-contact-details) | The contact details of the guest |
| primaryPhone | string                                                                | The primary phone number of the guest             |
| address      | [Address](../../development-reference/address-format.md)              | The address of the guest                          |
| isAnonymised  | boolean                                                              | Whether or not the guest details have been anonymised      |
| createdDate  | datetime                                                              | The date & time the venue guest was created       |
| modifiedDate | datetime                                                              | The date & time the venue guest was last modified |

## Guest Contact Details

| Property     | Type     | Description                                                  |
| ------------ | -------- | ------------------------------------------------------------ |
| id           | integer  | The unique id of the [contact](../../contact/get-contact.md) |
| firstName    | string   | The first name of the contact                                |
| lastName     | string   | The last name of the contact                                 |
| email        | string   | The email address of the contact                             |
| phone        | string   | The mobile phone number of the contact                       |
| createdDate  | datetime | The date & time the contact was created                      |
| modifiedDate | datetime | The date & time the contact was last modified                |
