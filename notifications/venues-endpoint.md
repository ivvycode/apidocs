# Invoice Endpoint

This endpoint will trigger when booking, accommodation or reservations have been created / modified. <ul><li>Booking is Added</li><li>Booking is Updated</li><li>Booking is Deleted</li><li>Booking Accommodation is Added</li><li>Booking Accommodation is Updated</li><li>Booking Accommodation is Deleted</li><li>Booking Room Reservation is Added</li><li>Booking Room Reservation is Updated</li><li>Booking Room Reservation is Deleted</li><li>Booking Moved <i>- A special notification to handle when a booking in iVvy has been moved.</i></li></ul>

## Booking is Added

### Subject
BookingAdded

### Body
```json
{
    "data": {... JSON Response from getBooking API }
}
```

## Booking is Updated

### Subject
BookingUpdated

### Body

```json
{
    "data": {... JSON Response from getBooking API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Booking is Moved

### Subject
BookingMoved

### Body

```json
{
    "data": {... JSON Response from getBooking API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Booking is Deleted

### Subject
BookingDeleted

### Body

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

## Booking Accommodation is Added

### Subject
BookingAccommodationAdded

### Body

```json
{
    "data": {... JSON Response from getBookingAccommodationList API }
}
```

## Booking Accommodation is Updated

### Subject
BookingAccommodationUpdated

### Body

```json
{
    "data": {... JSON Response from getBookingAccommodationList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Booking Accommodation is Deleted

### Subject
BookingAccommodationDeleted

### Body

```json
{
    "venueId": 123,
    "bookingId": 234,
    "bookingStatus": 2,
    "accommodationId": 567,
}
```

## Booking Room Reservation is Added

### Subject
BookingRoomReservationAdded

### Body

```json
{
    "data": {... JSON Response from getBookingRoomReservationList API }
}
```

## Booking Room Reservation is Updated

### Subject
BookingRoomReservationUpdated

### Body

```json
{
    "data": {... JSON Response from getBookingRoomReservationList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Booking Room Reservation is Deleted

### Subject
BookingRoomReservationDeleted

### Body

```json
{
    "venueId": 123,
    "bookingId": 234,
    "bookingStatus": 2,
    "reservationId": 567,
    "roomIds": [123, 456]
}
```
