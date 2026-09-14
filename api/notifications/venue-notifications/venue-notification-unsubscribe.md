# Unsubscribe

## Unsubscribe From Venue Notification

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/venue?action=unsubscribeFromNotification`

Removes an existing notification subscription for a specific venue.

The API key must have access to the specified venue and must be the same key that was used to create the subscription.

#### Request Body

| Name                                       | Type    | Description                                                    |
| ------------------------------------------ | ------- | -------------------------------------------------------------- |
| venueId<mark style="color:red;">\*</mark>  | integer | The unique identifier of the venue to unsubscribe from         |
| endpoint<mark style="color:red;">\*</mark> | string  | The HTTPS URL currently receiving notifications for this venue |

{% tabs %}
{% tab title="200 " %}
```json
{
    "result": 1
}
```
{% endtab %}
{% endtabs %}

This endpoint removes an existing notification subscription for the specified venue and endpoint. Once unsubscribed, notifications for this venue will no longer be delivered to that endpoint.

## Returns

| Property | Type    | Description                                                     |
| -------- | ------- | --------------------------------------------------------------- |
| result   | integer | A status code indicating the outcome of the unsubscribe request |

## Result Values

| Value | Status               | Description                                                                    |
| ----- | -------------------- | ------------------------------------------------------------------------------ |
| 1     | Success              | The subscription has been removed and notifications will no longer be sent     |
| 2     | Not Requested        | The endpoint was not included in the request                                   |
| 3     | Unknown Error        | An unexpected error occurred. Contact iVvy support if this persists            |
| 4     | Not Found            | No subscription exists for this venue and endpoint combination                 |
| 5     | Incorrect Source     | You must unsubscribe using the same API key that created the subscription      |
| 6     | Status Not Confirmed | The subscription cannot be removed until the initial confirmation is completed |
