## What is changing?

We’ve identified an unintended behaviour in our API where deleted contacts and companies are still being returned. To correct this, we’re updating the API to exclude these records.

Effective from 4th November 2025, contacts and companies in a deleted state will no longer be returned.

## How might you be affected?

If you currently use the [getContact](../../contact/get-contact.md), or [getCompany](../../contact/get-company.md) endpoints to retrieve contact or company records, please note that deleted records will no longer be included in responses after this update.

## What is changing in the iVvy API?

Responses from the [getContact](../../contact/get-contact.md), and [getCompany](../../contact/get-company.md) endpoints will exclude records marked as deleted.

## What should you do?
We recommend reviewing any logic in your integration that may rely on deleted records being returned, and ensuring your systems handle this change appropriately.

If you have any questions or concerns regarding this API change, please don't hesitate to reach out to our dedicated support team at support@ivvy.com.