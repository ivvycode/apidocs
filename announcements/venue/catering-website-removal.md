# Removal of Catering Website / Booking Attendees APIs

## What is changing?

iVvy is discontinuing the catering website feature. As part of this change, the booking attendee endpoints used to manage catering website attendees will be removed, and catering website related properties will be removed from the booking and venue endpoints.

Effective from 3rd November 2026, these changes will take place.

## How might you be affected?

You will be affected by this change if you use the iVvy API in the following ways:

-   If you use the following endpoints to manage booking attendees, these will stop working.
    -   [Add or Update Booking Attendee](../../venues/getoraddbookingdata/add-or-update-booking-attendee.md)
    -   [Get Booking Attendee By Hash](../../venues/getoraddbookingdata/get-booking-attendee-by-hash.md)
    -   [Get Booking Attendee List](../../venues/getoraddbookingdata/get-booking-attendee-list.md)
-   If you use the catering website properties returned by [Get Booking](../../venues/getoraddbookingdata/get-booking.md) or [Get Venue](../../venues/venuedata/get-venue.md), these properties will no longer be returned.

## What is changing in the iVvy API?

### Endpoints being removed

-   [Add or Update Booking Attendee](../../venues/getoraddbookingdata/add-or-update-booking-attendee.md)
-   [Get Booking Attendee By Hash](../../venues/getoraddbookingdata/get-booking-attendee-by-hash.md)
-   [Get Booking Attendee List](../../venues/getoraddbookingdata/get-booking-attendee-list.md)

### Properties being removed

-   [Get Booking](../../venues/getoraddbookingdata/get-booking.md)
    -   hasCateringWebsite
    -   cateringWebsiteLogoId
    -   cateringWebsiteLogo
    -   cateringWebsiteBannerId
    -   cateringWebsiteBanner
    -   cateringWebsiteEventDesc
    -   cateringWebsiteEndNumDays
-   [Get Venue](../../venues/venuedata/get-venue.md)
    -   cateringWebsitePrimaryColour
    -   cateringWebsiteLogoId
    -   cateringWebsiteLogo
    -   cateringWebsiteBannerId
    -   cateringWebsiteBanner

## What should you do?

1.  Stop using the Add or Update Booking Attendee, Get Booking Attendee (By Hash), and Get Booking Attendee List endpoints.
2.  Stop relying on the catering website properties listed above in your integration.

If you have any questions or concerns regarding this API change, please don't hesitate to reach out to our dedicated support team at support@ivvy.com.
