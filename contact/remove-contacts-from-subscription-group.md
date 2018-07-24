# Remove Contacts From Subscription Group

### Description

Remove contact details from subscription group.

### API URL

`[PlatformAddress]/api/1.0/contact?action=removeContactsFromSubscriptionGroup`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| contacts | The contact identifiers to unsubscribe from the group | Required | integer \(This is an array of contact identifiers\) |
| group | The subscription group identifier to remove the contacts from | Required | integer |

### Returns

An array of objects with the following properties

| Property | Description |
| --- | --- |
| contactId | The contact this result is for |
| status | If the contact was removed from the group or not |

Removes a number of contacts from a subscription group. This call is very similar to the [addContactsToSubscriptionGroup](add-contacts-to-subscription-group.md) call. It takes the same parameters and returns the same result.

