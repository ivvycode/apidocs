# CRM Integrations

CRM Integrations typically have different modules completed in them for transfer. 
* [Contacts](../../use-cases/crm-systems.md#Contacts)
* [Contact Emails](../../use-cases/crm-systems.md#Contact-Emails)
* [Events Software Users](../../use-cases/crm-systems.md#Event-Software-Users)
  * [Event Registrations](../../use-cases/crm-systems.md#Event-Registrations)
  * [Events](../../use-cases/crm-systems.md#Events)
  * [Event Attendees](../../use-cases/crm-systems.md#Event-Attendees)
* [Venues Software Users](../../use-cases/crm-systems.md#Venue-Software-Users)
  * [Companies](../../use-cases/crm-systems.md#Companies)
  * [Quotes & Bookings](../../use-cases/crm-systems.md#Quotes-and-Bookings)

# Contacts
Contacts are preferred to be transferred two ways between iVvy and the CRM system so that both systems are always kept up to date. 

It is important to remember that iVvy uses three fields to uniquely identify a contact: first name, last name and email. Other systems may not use the same identifiers, so it is recommended that a constant identifier is used (such as a contact ID) to make a permanent pairing of the contacts. iVvy does have a field to store a externalId that our integrations typically use to store the contact ID from the other system. 

Typical endpoints used when doing a 2 way contact sync. 
* [Get Contact List](../../contact/get-contact-list.md): Using this call with a filter of modifiedDate can give you the list of contacts that were modified in iVvy since the last sync. This minimises the amount of time that is spent comparing the contacts between the two systems. You may or may not also use the get Contact action which returns a single contact. 
* [Add or Update Contact](../../contact/add-or-update-contact.md) for when the contacts are being synced back into iVvy.
* [Get subscription group](../../contact/get-subscription-group-list.md) list and [add Contacts to subscription group](../../contact/add-contacts-to-subscription-group.md) if the integration will be supporting syncing of subscription groups. 

Remember to provide a method to map custom fields between the two systems if they are also being synced in the integration. 

# Contact Emails
As an email is usually stored against a singular action in iVvy, they cannot be received into iVvy from a third party. So contact emails are a one way sync out of iVvy and into the CRM so that the CRM has a comprehensive history of all correspondence sent to the contact. 

Typical endpoints used when doing an email sync from iVvy to a CRM:
* [Get Email Log List](../../account/get-email-log-list.md) returns a collection of the emails that have been sent. The content in the body in returned HTML format so it is wise to consider this when syncing the emails into a third party system. 

# Event Software Users
If completing a integration for Events users, these are some optional modules that have been popular demand. 

## Event Registrations
Event registrations are usually synced into the CRM as opportunities. This is normally optional so that the user can use the CRM portion and not be forced into this feature if they do not wish to use it. 

This is associated with the revenue of event registrations being displayed in the CRM system so that more accurate forecasting is completed. It also attaches to the contacts/companies history so that the CRM user can see an accurate historic relationship with the contact/company. This is a one way sync out of iVvy and into the CRM system. 

Typical Endpoints used when doing an Event Registration syncs into Opportunities in a CRM. 
* [Get Registration List](../../events/get-registration-list.md) can be used to fetch the latest created and modified event registrations from the iVvy system. 

Important point to remember is that returned event registrations include both delegate and exhibitor registrations. The data may be filtered depending on which is being targeted. Typical iVvy integrations include both. For a list of registration status they can be found under [Registration Current Status Details](../../events/get-registration-list.md#registration-current-status-details). 

Usually only paid “completed” status registrations would be synced, because until payment is received they are not guaranteed as income.

## Events 
Events are synced one way out of iVvy and into CRM campaigns. This is normally optional so that the user can use the CRM portion and not be forced into this feature if they do not wish to use it. 

This gives the CRM user access to a comprehensive history of what events took place for their clients, and which of the contacts (refer campaign members) actually attended their events. This gives a more comprehensive report of the history and relationship with the customer in the CRM. 

Typical Endpoints used when syncing events into a CRM. 
* [Get Event List](../../events/get-event-list.md) returns a list of events in the iVvy account. These can then be synced into the corresponding CRM system. 

## Event Attendees
Attendees in an iVvy event are synced against the campaign in the CRM as an attendee member. This is included in the optional “Events (campaigns)” module. Part of this sync includes keeping the invitation and attendance status periodically up to date.

Typical Endpoints used when syncing event members into a CRM. 
* [Get Invited Contact List](../../events/get-invited-contact-list.md) gives a list of contacts invited to the event. This action will return a response on if they clicked yes, no or haven’t responded yet, however it also updates a registration ID field when the contact progresses onto a registration. 
* [Get Attendee List](../../events/get-attendee-list.md) will give a list of contacts that have registered for the event. 

Event Registration Progress:
Initially a contact would start as an invitation with the following invitation status:  
* U = Undecided
* Y = Yes
* N = No

If the attendee has clicked yes than they will be now found in the attendee list as they have completed their registration. Once on the attendee list (meaning they will attend) the “hasAttended” and “sessionHasAttended” flags will verify if the user registered but did or did not attend. 

One point to remember is that if the event is not invite only, attendees can still register that haven’t been invited so there may be records in the attendee list that are not in the invited contact list that need to be considered. 

# Venue Software Users
If completing a integration for Venues users, these are some optional modules that have been popular demand. 

## Companies
The venues software has a component to store companies against contacts (whereas events does not) so a two way company sync (or as some CRMs refer to them as accounts) to keep the two systems up to date. The same as contacts, a company has an externalID field in iVvy that can be used as the constant to map the company together so if there is a name change, then the two companies are still connected and can be kept up to date. 

Typical Endpoints used when doing a Company sync
* [Get Company List](../../contact/get-company-list.md) and [Get Company](../../contact/get-company.md) if completing company syncs. 
* [Add or Update Company](../../contact/add-or-update-company.md), if sending data back from the third party CRM. 

## Quotes and Bookings
Venues may wish for their quotes and bookings to appear in their CRM against the contact / company as an Opportunity. This is usually “optional” so that if the venue wishes to use the CRM, they aren’t forced to use the bookings / quotes module if they do not wish to. 

iVvy does not allow for quotes/bookings to be pushed back into the system, and the data in an opportunity does not usually meet the minimum requirements of a quote or booking in the iVvy system so it’s completed as a one way sync out of iVvy and into the CRM System. 

Typical Endpoints used when doing a Quotes / Bookings Sync
* [getBookingListForAccount](../../venues/get-booking-list-for-account.md) (this returns bookings for all venues) [getBookingList](../../venues/get-booking-list.md) (returns all bookings for a single venue) or [getBooking](../../venues/get-booking.md) (returns a single booking) can be used to source a list of quotes and bookings out of a venue.  To differentiate between a quote and a booking the current status will identify if its Prospective (quote) or Tentative / Confirmed (Booking). 

To get the latest bookings that have been created or modified, the result can be filtered by a modifiedDateAfter parameter. 