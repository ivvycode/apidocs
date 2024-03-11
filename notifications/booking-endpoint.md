# Invoice Endpoint

This endpoint will trigger when booking, accommodation or reservations have been created / modified.

Here are the `Body` of the example notification messages after parse.

## Booking is Added
```json
{
    "data": {... JSON Response from getBooking API }
}
```
Subject: **BookingAdded**

## Booking is Updated
```json
{
    "data": {... JSON Response from getBooking API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **BookingUpdated**


## Booking is Moved
```json
{
    "data": {... JSON Response from getBooking API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **BookingMoved**


## Booking is Deleted
```json
{
    "venueId": 123,
    "bookingId": 234,
    "bookingStatus": 2,
    "accommodationIds": [567, 789],
    "roomReservationIds": [],
    "sessionIds": [789, 567]
}
```
Subject: **BookingDeleted**

## Booking Accommodation is Added
```json
{
    "data": {... JSON Response from getBookingAccommodationList API }
}
```
Subject: **BookingAccommodationAdded**


## Booking Accommodation is Updated
```json
{
    "data": {... JSON Response from getBookingAccommodationList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **BookingAccommodationUpdated**

## Booking Accommodation is Deleted
```json
{
    "venueId": 123,
    "bookingId": 234,
    "bookingStatus": 2,
    "accommodationId": 567,
}
```
Subject: **BookingAccommodationDeleted**

## Booking Room Reservation is Added
```json
{
    "data": {... JSON Response from getBookingRoomReservationList API }
}
```
Subject: **BookingRoomReservationAdded**


## Booking Room Reservation is Updated
```json
{
    "data": {... JSON Response from getBookingRoomReservationList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **BookingRoomReservationUpdated**


## Booking Room Reservation is Deleted

```json
{
    "venueId": 123,
    "bookingId": 234,
    "bookingStatus": 2,
    "reservationId": 567,
    "roomIds": [123, 456]
}
```
Subject: **BookingRoomReservationDeleted**



