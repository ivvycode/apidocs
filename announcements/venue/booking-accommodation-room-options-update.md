# Breaking changes of Booking Accommodation APIs

## What is changing?

We are updating our API to modify a key value. Effective from 22 October 2024, the key "numOptionsPerRoom" will be changed to "numOptions" in the [getBookingAccommodationList](/venues/accommodation/get-booking-accommodation-list) and [addOrUpdateBookingAccommodation](/venues/accommodation/add-or-update-booking-accommodation) endpoints.

## How might you be affected?

If you currently use the [getBookingAccommodationList](/venues/accommodation/get-booking-accommodation-list)  and [addOrUpdateBookingAccommodation](/venues/accommodation/add-or-update-booking-accommodation) endpoints, please be aware that the key "numOptionsPerRoom" will no longer be recognized.


## What is changing in the iVvy API?

- [getBookingAccommodationList](/venues/accommodation/get-booking-accommodation-list)
- [addOrUpdateBookingAccommodation](/venues/accommodation/add-or-update-booking-accommodation)

The key "numOptionsPerRoom" will be replaced with "numOptions".

## What should you do?

Please update your applications and integrations to use the new key "numOptions" in place of "numOptionsPerRoom" for the [getBookingAccommodationList](/venues/accommodation/get-booking-accommodation-list) and [addOrUpdateBookingAccommodation](/venues/accommodation/add-or-update-booking-accommodation) endpoints.

If you have any questions or concerns regarding this API change, please don't hesitate to reach out to our dedicated support team at support@ivvy.com.