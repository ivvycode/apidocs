# Breaking changes of Room Reservation APIs

## What is changing?

iVvy currently records guest details on room reservations as contacts. See [getBookingRoomReservationList#guest](https://developer.ivvy.com/venues/accommodation/get-booking-room-reservation-list#guest).

These contact details are currently contacts in the crm database. iVvy is planning a change to the system in the future that will remove these contacts from the crm database, and replace them with a new database. The contact details, including the unique id of the contact, will remain unchanged during this transition.

iVvy is also planning future product changes that will make it possible to anonymise guest details within the system.

## How might you be affected?

You might be affected by this change in the following ways if you use the iVvy API:
-   If you use the following contact APIs to manage guest details, these will stop working.
	-   [getContactList](https://developer.ivvy.com/contact/get-contact-list) or [getContact](https://developer.ivvy.com/contact/get-contact) to fetch guest details
	-   [addOrUpdateContact](https://developer.ivvy.com/contact/add-or-update-contact) to add/update guest details.
-   The contact messages published to subscribed https endpoints will no longer work for guests.
	-   ContactAdded
	-   ContactUpdated
	-   ContactDeleted
-   If you update systems with the guest details, this could result in invalid data once the guest is anonymised in iVvy.
-   If you use the unique guest id to add new guests to reservations, the API request will fail if the guest has been anonymised in iVvy.


## What is changing in the iVvy API?

### getBookingRoomReservationList

[getBookingRoomReservationList](https://developer.ivvy.com/venues/accommodation/get-booking-room-reservation-list)
The following changes are being made to the Guest object described here: [getBookingRoomReservationList#guest](https://developer.ivvy.com/venues/accommodation/get-booking-room-reservation-list#guest)
1.  There is a possibility that *isAnonymised* can be true, in which case the personal guest contact details will be empty as per documentation.
2.  The contact property will be removed.
This will apply to all properties that are of type Guest.


### addOrUpdateBookingRoomReservation

[addOrUpdateBookingRoomReservation](https://developer.ivvy.com/venues/accommodation/add-or-update-booking-room-reservation)

The following changes are being made to the Guest object described here: [addOrUpdateBookingRoomReservation#guest](https://developer.ivvy.com/venues/accommodation/add-or-update-booking-room-reservation#guest)
1.  The *contact* property will be removed.

*Anonymised* guests cannot be added to a reservation. If you use the guest id to add a new guest to the reservation (any *Guest* type property) the request will fail and an error will be returned. The best way to avoid this error is to never use the guest id to add new guests to a reservation, but instead always pass the contact details. This also applies when adding a new reservation. Changes to an *existing* anonymised guest on a reservation will be ignored by iVvy and not produce an error.

If a guest has been *anonymised* in iVvy, and you pass the contact details of that guest then a new guest contact will be created with a new unique id.

**Response Object**

The *contactId* property of the *guest* objects (mainGuest, guest, additionalGuests) will be removed. Use *guestContactId* instead.

### updateBookingRoomReservationGuestContact

*Anonymised* guests cannot be updated. An error response will be returned when attempting to update an *anonymised* guest contact.

### getContactList, getContact

[getContactList](https://developer.ivvy.com/contact/get-contact-list)
[getContact](https://developer.ivvy.com/contact/get-contact)

These api actions will no longer return guests. There is no alternative to fetch guest details besides using the reservation APIs.

### addOrUpdateContact
[addOrUpdateContact](https://developer.ivvy.com/contact/add-or-update-contact) can no longer be used for guests.

## What should you do?
1.  Stop using the contact APIs for guests. Instead, use the above room reservation APIs to manage guest details.
2.  Stop subscribing to contact messages for guest details. Instead, subscribe to messages about room reservations for guest details.
3.  Stop using the *contact* property of the Guest object. Instead, use the *guestContact* property.
4.  Decide how an anonymised guest impacts your system(s). *isAnonymised* is a *readonly* property. Once the guest is anonymised in iVvy, the original personal identifiable information cannot be retrieved.
5.  Stop using guest *ids* to add guests to a reservation (including when adding a new reservation). Instead, always pass the contact details.
6.  Check the permissions assigned to your api key in case you intend to use the new updateBookingRoomReservationGuestContact api.
7.  Stop using contactId property from addOrUpdateBookingRoomReservation api response, instead use guestContactId.
