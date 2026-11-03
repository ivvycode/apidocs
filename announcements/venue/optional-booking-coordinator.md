# Optional Booking Coordinator

## What is changing?

The coordinator of a booking (_bookedById_) is now optional when adding or updating a booking through the API. Integrations no longer need to choose a coordinator when they create a booking; the venue can assign one later.

Bookings created through the Booking Engine Form could already have no coordinator. Bookings without a coordinator can now be created and updated through the API as well.

## How might you be affected?

You might be affected if you read bookings through the API:

-   [Get Booking](../../venues/getoraddbookingdata/get-booking.md) and [Get Booking List](../../venues/getoraddbookingdata/get-booking-list.md) return _bookedById_ as null when a booking has no coordinator. Until now these bookings returned _bookedById_ as 0.
-   [Get Booking](../../venues/getoraddbookingdata/get-booking.md) returns _bookedByUser_ as null when a booking has no coordinator.

## What is changing in the iVvy API?

### addOrUpdateBooking

[Add or Update Booking](../../venues/getoraddbookingdata/add-or-update-booking.md#booking-coordinator)

-   _bookedById_ is no longer required when adding a new booking.
-   A booking without a coordinator can be updated without setting one.
-   Setting _bookedById_ to null removes the coordinator from the booking.
-   When _bookedById_ is set, it is validated as before.

### getBooking, getBookingList

-   _bookedById_ is null when the booking has no coordinator.
-   _bookedByUser_ (getBooking only) is null when the booking has no coordinator.

## What should you do?

1.  Treat a null _bookedById_ as "no coordinator assigned". If your integration checks for 0, check for null as well.
2.  If you assign a placeholder coordinator only because the API required one, you can now leave _bookedById_ out of the request.
