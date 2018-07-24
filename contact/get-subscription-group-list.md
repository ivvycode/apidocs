# Get Subscription Group List

## Description

Subscription Groups are a feature that enables customers to segment their contacts into groups. These groups can then used for a range of purposes, including email and sms marketing, restricting access to event ticket types and content pages plus more.

## API URL

`[PlatformAddress]/api/1.0/contact?action=getSubscriptionGroupList`

## Returns

An array with the following properties

| Property | Description |
| --- | --- |
| id | The subscription group identifier |
| groupName | The name for the group |
| memberCount | The number of contacts in the group |
| tagColour | The designated colour for the group |

Returns an array of subscription groups available on the account.

