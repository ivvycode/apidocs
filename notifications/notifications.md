# Notifications

This documentation will explain iVvy notifications. In our system, it is referred to as a subscription and each event type is a notification.

For terminology, you subscribe to an endpoint. There are several endpoints available and will provide the changes related to that specific endpoint.

## Table Of Contents

- [Notifications](#notifications)
  - [Table Of Contents](#table-of-contents)
  - [Subscriptions](#subscriptions)
    - [Testing](#testing)
    - [Subscribing To A Notification](#subscribing-to-a-notification)
    - [Subscribe](#subscribe)
    - [Unsubscribe](#unsubscribe)
  - [Endpoints](#endpoints)
    - [Company Endpoint](#company-endpoint)
    - [Contact Endpoint](#contact-endpoint)
    - [Opportunity Endpoint](#opportunity-endpoint)
    - [Invoice Endpoint](#invoice-endpoint)
    - [Booking Endpoint](#booking-endpoint)
  - [Example](#example)
  - [Message Details](#message-details)
  - [Source Type](#source-type)

## Subscriptions

iVvy offers notifications that will send you details of a specific object that you wish to subscribe to. There are several notifications available and you may subscribe and unsubscribe to whichever notification is necessary for your development.

### Testing

You can test using this fantastic website:

[https://webhook.site/](https://webhook.site/)

This website will assist you in receiving webhook information during your testing.

### Subscribing To A Notification

Following on the instructions we have available on our website:

[https://developer.ivvy.com/getting-started](https://developer.ivvy.com/getting-started)

You can use the following subscription endpoints:

**Request Body**

The request body to be provided to the endpoints is a JSON body with the key being the name of the notification endpoint you wish to subscribe to / unsubscribe from. And the value being the URL you are using to receive our notification.

The same object is required when interacting with either endpoint described below. The notification endpoints available are described [below](#notifications).

```json
{
  "[ENDPOINT NAME]": "YOUR WEBHOOK URL"
}
```

### Subscribe
/api/1.0/account?action=subscribeToNotifications - POST

This endpoint will allow you to subscribe to a new notification type.

**Response**

The response that you will receive will be very similar to this. It will show you the current status of all of the notifications that you currently subscribe to. In the example below, this is a response when subscribed to the companies notification.
```json
{
  "eventsSuccess": false,
  "eventsTopicId": null,
  "venuesSuccess": false,
  "venuesTopicId": null,
  "paymentsSuccess": false,
  "paymentsTopicId": null,
  "crmSuccess": false,
  "crmTopicId": null,
  "contactsSuccess": false,
  "contactsTopicId": null,
  "companiesSuccess": true,
  "companiesTopicId": "arn:aws:sns:ap-southeast-2:2:iVvy_Account_41_d7_NotifCompanies"
}
```

When you have subscribed to a notification, the endpoint you have provided will receive a message containing specific information about the notification you have subscribed to. Below is an example of a message from the iVvy API.
```json
{
  "Type": "SubscriptionConfirmation",
  "MessageId": "9a55edb6-b3e8-4cef-9eee-6d302d24c5ac",
  "Token": "2336412f37fb687f5d51e6e2425f004ae03ffa22ff5caccf7d0",
  "TopicArn": "arn:aws:sns:ap-southeast-2:232528047142:iVvy_Account5_d7336c818a0bf60d087_NotifCompanies",
  "Message": "You have chosen to subscribe to the topic arn:aws:sns:ap-southeast-2:232528047142:iVvy_Account5_d7336c818a0bf60d087_NotifCompanies.\nTo confirm the subscription, visit the SubscribeURL included in this message.",
  "SubscribeURL": "https://sns.ap-southeast-2.amazonaws.com/?Action=ConfirmSubscription&TopicArn=arn:aws:sns:ap-southeast-2:232528047142:iVvy_Account_818a0bf60d087_NotifCompanies&Token=2336412",
  "Timestamp": "2020-09-14T00:10:13.086Z",
  "SignatureVersion": "1",
  "Signature": "bvcrDYRbbqYK6aXAOAIK0e+W/Bs0kr6VQMyoNQ==",
  "SigningCertURL": "https://sns.ap-southeast-2.amazonaws.com/SimpleNotificationService-a89c941702d737128f7b6.pem"
}
```

In the JSON object above, you’ll notice that there is a message and it will say something similar to the below:

_To confirm the subscription, visit the SubscribeURL included in this message_

There is a **SubscribeURL** attribute. You will need to contact this endpoint which will complete the registration of the subscription for that URL. You will not receive any notifications until you have contacted this endpoint.

### Unsubscribe

/api/1.0/account?action=unsubscribeFromNotifications - POST

_Note: Use the body request that you used in the subscribe endpoint._

Should you wish to no longer receive notifications of a particular type.

**Response**

```json
{
  "eventsResult": 2,
  "venuesResult": 2,
  "paymentsResult": 2,
  "crmResult": 2,
  "contactsResult": 2,
  "companiesResult": 1
}
```

The response example above shows the result of unsubscribing each endpoint. The integer value will be one of the following:

| Value | Short                 | Description   |
| ----- | --------------------- | ------------- |
| 1     | Success               | The notification endpoint has been unsubscribed, and will no longer receive notifications     |
| 2     | Not Requested         | The notification endpoint was not in the api request                                          |
| 3     | Unknown Error         | An unknown error has occurred, contact iVvy tech support                                      |
| 4     | Not Found             | The notification endpoint was not found in the list of subscribed endpoints                   |
| 5     | Incorrect Source      | You must unsubscribe with the API key that was used to subscribe the notification endpoint    |
| 6     | Status Not Confirmed  | The notification endpoint cannot be unsubscribed until it has been confirmed                  |

## Endpoints

### Company Endpoint

| Endpoint          | Notification Sends    |
| ----------------- | --------------------- |
| companiesEndpoint | This notification will be sent when a company has been modified or created. <ul><li>Company has been updated.</li><li>Company has been created.</li><li>Company has been deleted.</li></ul> |

### Contact Endpoint

| Endpoint          | Notification Sends    |
| ----------------- | --------------------- |
| contactsEndpoint  | This notification will be sent when a contact has been modified or created. <ul><li>Contact has been updated</li><li>Contact has been created</li><li>Contact has been deleted</li></ul> |

### Opportunity Endpoint

| Endpoint          | Notification Sends    |
| ----------------- | --------------------- |
| crmEndpoint       | This notification will be sent when an opportunity has been modified. <ul><li>Opportunity is updated</li><li>Opportunity is added</li><li>Opportunity is deleted</li><li>Tasks is updated</li><li>Task is created</li><li>Task is deleted</li><li>Activity is updated</li><li>Activity is created</li><li>Activity is deleted</li></ul> |

### Invoice Endpoint

| Endpoint          | Notification Sends    |
| ----------------- | --------------------- |
| paymentsEndpoint  | This notification will occur when a modification to an invoice occurs. This includes when payments are applied against an invoice. <ul><li>Invoice is created</li><li>Invoice is updated</li><li>Payment is applied to invoice</li></ul> |

### Booking Endpoint

| Endpoint          | Notification Sends    |
| ----------------- | --------------------- |
| venuesEndpoint    | This endpoint will trigger when booking, accommodation or reservations have been created / modified. <ul><li>Booking is Added</li><li>Booking is Updated</li><li>Booking is Deleted</li><li>Booking Accommodation is Added</li><li>Booking Accommodation is Updated</li><li>Booking Accommodation is Deleted</li><li>Booking Room Reservation is Added</li><li>Booking Room Reservation is Updated</li><li>Booking Room Reservation is Deleted</li><li>Booking Moved <i>- A special notification to handle when a booking in iVvy has been moved.</i></li></ul> |


## Example

Generally, a notification message looks like below. "Body" within **Message** are different for different type of Notifications.

```json
{
  "Type": "Notification",
  "MessageId": "1bca0cbf-8790-506f-a983-52d7cc7d32d9",
  "TopicArn": "arn:aws:sns:ap-southeast-2:232528047142:iVvy_Account_14_d4959ffe27f4a760733babdf1fa7fbbd354d4f62_NotifCompanies",
  "Message": "{\"TxnId\":\"b898c04362bcbfe984f1867ce7db5599\",\"Region\":\"stage\",\"Timestamp\":1710115244,\"AccountId\":\"14\",\"Subject\":\"CompanyAdded\",\"Body\":\"{\\\"data\\\":{\\\"id\\\":60825,\\\"externalId\\\":null,\\\"businessName\\\":\\\"Test Company 123\\\",\\\"tradingName\\\":\\\"Trading Name\\\",\\\"businessNumber\\\":\\\"ABN123\\\",\\\"phone\\\":\\\"\\\",\\\"otherPhone\\\":\\\"\\\",\\\"fax\\\":\\\"\\\",\\\"website\\\":\\\"\\\",\\\"email\\\":\\\"\\\",\\\"address\\\":{\\\"line1\\\":\\\"\\\",\\\"line2\\\":\\\"\\\",\\\"line3\\\":\\\"\\\",\\\"line4\\\":\\\"\\\",\\\"city\\\":\\\"\\\",\\\"stateCode\\\":\\\"\\\",\\\"countryCode\\\":\\\"AU\\\",\\\"postalCode\\\":\\\"\\\"},\\\"modifiedDate\\\":\\\"2024-03-11 00:00:44 UTC\\\",\\\"primaryAccountManager\\\":{\\\"id\\\":50476,\\\"firstName\\\":\\\"API\\\",\\\"lastName\\\":\\\"Test\\\",\\\"email\\\":\\\"david.tannock@ivvy.com\\\"},\\\"secondaryAccountManager\\\":null,\\\"industry\\\":{\\\"id\\\":369,\\\"name\\\":\\\"Banking\\\"},\\\"primaryContact\\\":{\\\"id\\\":7474181,\\\"firstName\\\":\\\"test\\\",\\\"lastName\\\":\\\"test\\\",\\\"email\\\":\\\"test01@ivvy.com\\\",\\\"phone\\\":\\\"078 0895 8308\\\"},\\\"isAgent\\\":0,\\\"parentCompanyId\\\":0,\\\"leftValue\\\":1,\\\"rightValue\\\":2,\\\"depth\\\":0,\\\"rootId\\\":60825,\\\"commissionSpace\\\":null,\\\"commissionSpaceType\\\":null,\\\"commissionFood\\\":null,\\\"commissionFoodType\\\":null,\\\"commissionBeverage\\\":null,\\\"commissionBeverageType\\\":null,\\\"commissionAudioVisual\\\":null,\\\"commissionAudioVisualType\\\":null,\\\"commissionAccommodation\\\":null,\\\"commissionAccommodationType\\\":null,\\\"iataNumber\\\":null,\\\"customFields\\\":[{\\\"fieldId\\\":64,\\\"displayName\\\":\\\"t\\\",\\\"value\\\":\\\"\\\"},{\\\"fieldId\\\":67,\\\"displayName\\\":\\\"RB-1952 test 1\\\",\\\"value\\\":\\\"\\\"},{\\\"fieldId\\\":68,\\\"displayName\\\":\\\"RB-1952 test 2\\\",\\\"value\\\":[\\\"\\\"]},{\\\"fieldId\\\":76,\\\"displayName\\\":\\\"Upload file\\\",\\\"value\\\":null},{\\\"fieldId\\\":169753,\\\"displayName\\\":\\\"RB-3526 test\\\",\\\"value\\\":\\\"2024-03-11 14:00:00 UTC\\\"}]}}\",\"SourceType\":0,\"SourceInfo\":null,\"Signature\":\"jbOmjGh1CmyA\\/Z1vS+gnTidrTD\\/vxX7wZtmRmb8N1M7NxTqgpiGOErR8zAvTtfQqVH0sU6yCQkXykEOrmCIT1u3pC9j34IZQKgAMv859xXBSCpx0SXBNqo7dyXT8zAq5p6vW\\/1BGuIWbooaNFB3KNmWmc8y9fMs0akFINuF2kSS6AndnD2zwtIVxZ3jIs8eFSBroEVNOX1YaaGKOulIjQvdMsk7Ge0UGCAba36izHf65Q5riEjrqz0W62OseHJseLZIVRRjlW+4VsYdx2sq1cCXYz1M3Muw0iTNUvHcqAIEG18cF6+tNuqPX4ilDzYzc4udEOv1z8X8+Un5kmqO9Uw==\",\"SigningPublicKeyPath\":\"\\/accounts\\/14\\/1537854341\\/notifcert.txt\"}",
  "Timestamp": "2024-03-11T00:00:45.569Z",
  "SignatureVersion": "1",
  "Signature": "k1fv23ZAC0tYVn8UaFZHcwJQCH0LaubIz5219ziK/tn4uR7GlSi/h0A7XL3aibrVn5aU6LF3scYzXezw0N21EOD2VZohAY/oSgbqzwp+RECvbGs4kZuz8x+6lKYeem2TPEjsaPaFF+JuW7sSvTqZ8L2MZuxbCBXOuiuBl5hKF2va2Tkaiho0A+753AbQWL4hQjqxCCLb1UrglvgKTPfrg9Ew4x9FFe9tNjkh7utYYKI9fltcqp5Hk66E6ftsxsixBsa44t2cUCCOKFnleTH90sPgtWwBYazee4wdL/s+rsBLMxKPYTUcwTLc6TAqtE4N1V2xBILksFEBlG9nNGBLpg==",
  "SigningCertURL": "https://sns.ap-southeast-2.amazonaws.com/SimpleNotificationService-60eadc530605d63b8e62a523676ef735.pem",
  "UnsubscribeURL": "https://sns.ap-southeast-2.amazonaws.com/?Action=Unsubscribe&SubscriptionArn=arn:aws:sns:ap-southeast-2:232528047142:iVvy_Account_14_d4959ffe27f4a760733babdf1fa7fbbd354d4f62_NotifCompanies:a97813c2-7724-4f18-97a5-afd41258bd44"
}
```

## Message Details

| Property |  Description | Type |
| ----------------------- | ----------------------------------- | --------- |
| AccountId | The Account Id from where notification has been published | string |
| Body | The body of the notification. | string |
| Region | The region of the notification from where notification has been published | string |
| Signature | The cryptographic signature of the message | string |
| SigningPublicKeyPath | The path of the public certificate paired with the private key used to generate the signature.  | string |
| SourceInfo | Optionally the source of the message in JSON. E.g. API key for API source | string |
| SourceType | The source of the message | int |
| Timestamp | The timestamp of the notification  | string |
| TxnId | The Transaction id of the notification  | string |


## Source Type

| Value | Description |
| ----- | ------------ |
| 0 | Unknown |
| 1 | API |