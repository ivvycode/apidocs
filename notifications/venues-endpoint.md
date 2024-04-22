# Invoice Endpoint

This endpoint will trigger when booking, accommodation or reservations have been created / modified. <ul><li>Booking is Added</li><li>Booking is Updated</li><li>Booking is Deleted</li><li>Booking Session is Added</li><li>Booking Session is Updated</li><li>Booking Session is Deleted</li><li>Booking Accommodation is Added</li><li>Booking Accommodation is Updated</li><li>Booking Accommodation is Deleted</li><li>Booking Room Reservation is Added</li><li>Booking Room Reservation is Updated</li><li>Booking Room Reservation is Deleted</li><li>Booking Note is Added</li><li>Booking Note is Updated</li><li>Booking Note is Deleted</li><li>Booking Moved <i>- A special notification to handle when a booking in iVvy has been moved.</i></li><li>Space Blockout is Added</li><li>Space Blockout is Updated</li><li>Space Blockout is Deleted</li></ul>

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

## Booking Session is Added

### Subject
BookingSessionAdded

### Body
```json
{
    "data": {... JSON Response from getBookingSessionList API }
}
```

## Booking Session is Updated

### Subject
BookingSessionUpdated

### Body

```json
{
    "data": {... JSON Response from getBookingSessionList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Booking Session is Deleted

### Subject
BookingSessionDeleted

### Body

```json
{
    "venueId": 123,
    "bookingId": 234,
    "sessionId": 567
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


## Booking Note is Added

### Subject
BookingNoteAdded

### Body

```json
{
    "data": {... JSON Response from getBookingNoteList API }
}
```

## Booking Note is Updated

### Subject
BookingNoteUpdated

### Body

```json
{
    "data": {... JSON Response from getBookingNoteList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Booking Note is Deleted

### Subject
BookingNoteDeleted

### Body

```json
{
    "noteId": 123,
}
```

## Space Blockout is Added

### Subject
SpaceBlockoutAdded

### Body

```json
{
    "data": {... JSON Response from getSpaceBlockoutList API }
}
```

## Space Blockout is Updated

### Subject
SpaceBlockoutUpdated

### Body

```json
{
    "data": {... JSON Response from getSpaceBlockoutList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Space Blockout is Deleted

### Subject
SpaceBlockoutDeleted

### Body

```json
{
    "venueId": 123,
    "spaceBlockoutId": 234,
}
```

## Venue Guest is Anonymised

### Subject
VenueGuestAnonymised

### Body

```json
{
    "guestContactId":"3"
}
```