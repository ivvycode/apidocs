# Subscribe to Venue Notification

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=subscribeToNotifications" method="post" summary="Subscribe To Venue Notifications" %}
{% swagger-description %}
Creates a notification subscription for a specific venue.

The API key must have access to the specified venue for the subscription to be created.

Notifications are delivered via AWS SNS and follow the same structure as the account-level Notifications API.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" required="true" %}
The unique identifier of the venue to subscribe to
{% endswagger-parameter %}

{% swagger-parameter name="endpoint" type="string" in="body" required="true" %}
The HTTPS URL that will receive notification payloads
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
{
    "success": true,
    "topicId": "arn:aws:sns:ap-southeast-2:123456789012:venue-12345",
    "error": null
}
```
{% endswagger-response %}
{% endswagger %}

This endpoint creates a notification subscription for the specified venue. Once created, AWS SNS will send a `SubscriptionConfirmation` request to your endpoint. You must confirm the subscription by visiting the `SubscribeURL` included in that request before notifications will be delivered.

**Note:** Only HTTPS endpoints are supported. HTTP endpoints will be rejected.

## Returns

| Property | Type | Description |
| --- | --- | --- |
| success | boolean | Indicates whether the subscription was created successfully |
| topicId | string | The AWS SNS topic ARN associated with this subscription. Returns `null` if unsuccessful |
| error | string | A description of why the subscription failed. Returns `null` on success |

## Example Notification Payload

```json
{
    "Type": "Notification",
    "MessageId": "95df01b4-ee98-5cb9-9903-4c221d41eb5e",
    "TopicArn": "arn:aws:sns:ap-southeast-2:123456789012:venue-12345",
    "Subject": "booking.updated",
    "Message": "{\"TxnId\":\"ABC123\",\"SourceType\":\"venue\",\"VenueId\":12345}",
    "Timestamp": "2026-05-20T01:20:15.000Z",
    "SignatureVersion": "1",
    "Signature": "EXAMPLEw6JRN...",
    "SigningCertURL": "https://sns.ap-southeast-2.amazonaws.com/SimpleNotificationService.pem",
    "UnsubscribeURL": "https://sns.ap-southeast-2.amazonaws.com/?Action=Unsubscribe..."
}
```

## Error Response Example

When a subscription cannot be created, the response will include an error message:

```json
{
    "success": false,
    "topicId": null,
    "error": "The endpoint is already associated with another subscription."
}
```

### Common Errors

| Error | Description |
| --- | --- |
| The endpoint is already associated with another subscription | The URL is already subscribed to this or another venue |