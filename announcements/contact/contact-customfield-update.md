## What is changing?

We have identified an unintended behaviour in our API, where all custom fields (global and event-specific) are currently being returned when using certain endpoints. To address this, a change is planned to modify this behaviour to no longer return the event custom fields on contact API endpoints

Effective from 29th August 2023, the customFields object in the getContact and getContactList API endpoints will only return global custom fields associated with a contact, excluding any event-specific custom fields.

## How might you be affected?

If you currently use the [getContact](../../contact/get-contact.md) and [getContactList](../../contact/get-contact-list.md) APIs to retrieve event custom fields, please be aware that these endpoints will no longer return such information after the update.

## What is changing in the iVvy API?

- [getContact](../../contact/get-contact.md)
	- customFields object of this API endpoint will only return global custom fields of a contact and not return event specific custom fields
- [getContactList](../../contact/get-contact-list.md)
	- customFields object of this API endpoint will only return global custom fields of a contact and not return event specific custom fields

## What should you do?
1. Discontinue using [getContact](../../contact/get-contact.md) and [getContactList](../../contact/get-contact-list.md) for retrieving event custom fields.
2. Utilise [getAttendee](../../events/get-attendee.md) and/or [getAttendeeList](../../events/get-attendee-list.md) APIs to fetch the required event custom field data.
3. Confirm your API keys have access to the required API actions listed above

If you have any questions or concerns regarding this API change please don't hesitate to reach out to our dedicated support team at support@ivvy.com.