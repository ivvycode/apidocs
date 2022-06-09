# Get Booking Changelog List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getBookingChangelogList" method="post" summary="Get Booking Changelog List" %}
{% swagger-description %}
Get the list of a booking changelogs to which the user has access.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="path" %}
The id of the booking
{% endswagger-parameter %}

{% swagger-parameter name="orderBy" type="string" in="body" %}
Sort Results: Support Parameter 'name'
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of changelogs to get in a single call
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 100,
        "count": 2
    },
    "results": [
         {
            "id": 8,
            "venueId": 1,
            "bookingId": 4407,
            "beoId": 816,
            "sessionId": "2447",
            "recordedByUserId": "1",
            "refType": 3,
            "refId": 2447,
            "noteText": "Some Changes in Session",
            "createdDate": "2022-02-01 11:01:13 UTC",
            "modifiedDate": "2022-02-01 11:01:13 UTC"
        },
        {
            "id": 9,
            "venueId": 1,
            "bookingId": 4407,
            "beoId": 816,
            "sessionId": "2447",
            "recordedByUserId": "10",
            "refType": 3,
            "refId": 2447,
            "noteText": "Bit early in schedule",
            "createdDate": "2022-02-01 11:10:39 UTC",
            "modifiedDate": "2022-02-01 11:10:39 UTC"
        },
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be the list of booking changelogs.

## Example Request

```
{
	"venueId" : 1,
	"bookingId" : 4407,
    "perPage" : 100,
}
```

## Booking Changelog

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the booking changelog |
| venueId | integer | required | The id of the venue to which the bookign changelog belongs |
| bookingId | integer | required | The id of the booking to which the booking changelog belongs |
| beoId | integer | required | The id of the beo to which the booking changelog belongs |
| sessionId | integer | optional | The id of the session to which the booking changelog belongs |
| recordedByUserId | integer | required | The id of the user who recorded the booking changelog |
| refType | enum ([Booking Changelog Reference Type](get-booking-changelog-list.md#booking-changelog-reference-type)) | required | The reference type to which the booking changelog belongs |
| refId | integer | required | The reference Id of the booking changelog |
| noteText | string | required | The note text of the booking changelog |
| createdDate | timestamp | required | The date & time the booking changelog was created |
| modifiedDate | timestamp | required | The date & time the booking changelog was last modified |


## Booking Changelog Reference Type

| Value | Description |
| ----- | ---------------- |
| 1 | Booking |
| 2 | Accommodation |
| 3 | Session |
| 4 | Menu |
| 5 | Beverage |
| 6 | Resource |
| 7 | Product |
| 8 | Contact |
| 9 | Additional Item |
| 11 | Package |
| 12 | Setup Requirement |