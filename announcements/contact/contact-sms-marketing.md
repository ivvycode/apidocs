## What is changing?

We are updating our API to remove the smsStatus attribute. This change aligns with the removal of SMS marketing functionality in November 2025.

Effective from 30 June 2026, smsStatus will be removed from the following endpoints:

- [addOrUpdateContact](../../contact/add-or-update-contact.md)
- [getContact](../../contact/get-contact.md)

## How might you be affected?
If you use the [addOrUpdateContact](../../contact/add-or-update-contact.md) or [getContact](../../contact/get-contact.md) endpoints, the `smsStatus` attribute will no longer be available in requests or responses.

## What is changing in the iVvy API?
- The `smsStatus` attribute will be fully removed from the API schema.
- It will no longer be returned by the [getContact](../../contact/get-contact.md) and [getContactList](../../contact/get-contact-list.md) endpoint.
- Requests to [addOrUpdateContact](../../contact/add-or-update-contact.md) containing `smsStatus` will no longer be supported

## What should you do?
Please update your applications and integrations to remove all references to the `smsStatus` attribute before 30 June 2026.

If you have any questions or concerns regarding this API change please don't hesitate to reach out to our dedicated support team at support@ivvy.com.