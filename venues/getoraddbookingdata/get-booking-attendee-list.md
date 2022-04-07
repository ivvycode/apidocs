# Get Booking Attendee List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getBookingAttendeeList" method="post" summary="Get Booking ATttendee List" %}
{% swagger-description %}
Get the list of a booking attendees to which the user has access.
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
The number of attendees to get in a single call
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
            "id": "10",
            "venueId": "1",
            "bookingId": "4407",
            "firstName": "First",
            "lastName": "Last",
            "phone": "123456789",
            "email": "some@email.com",
            "dietaryRequirement": "Specific requirement",
            "isFromCateringWebsite": true,
            "menuItems": [
                {
                    "sessionId": "2447",
                    "menuId": "225",
                    "inventoryId": "14"
                },
                {
                    "sessionId": "2447",
                    "menuId": "226",
                    "inventoryId": "18"
                },
                {
                    "sessionId": "2448",
                    "menuId": "227",
                    "inventoryId": "20"
                }
            ]
        },
        {
            "id": "11",
            "venueId": "1",
            "bookingId": "4407",
            "firstName": "First 2",
            "lastName": "Last 2 ",
            "phone": "123456789",
            "email": "some2@email.com",
            "dietaryRequirement": "Specific requirement",
            "isFromCateringWebsite": true,
            "menuItems": [
                {
                    "sessionId": "2447",
                    "menuId": "225",
                    "inventoryId": "14"
                }
            ]
        },
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be the list of booking attendees to which the user has access. 

## Example Request

```
{
	"venueId" : 1,
	"bookingId" : 4407,
    "perPage" : 100,
	"orderBy": "name"
}
```

## Booking Attendee

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | integer | optional | The unique id of the booking attendee. |
| venueId | integer | required | The id of the venue to which the booking attendee belongs |
| bookingId | integer | required | The id of the booking. |
| firstName | string | required | The first name of the booking attendee. |
| lastName | string | required | The last name of the booking attendee. |
| phone | string | required | The phone number of the booking attendee. |
| email | string | required | The email address of the booking attendee. |
| isFromCateringWebsite | boolean | optional | Whether or not booking attedee recorded from catering website |
| dietaryRequirement | string | optional | The dietary requirements of the booking attendee. |
| menuItems | array | optional | The list of menu items that is included in the booking attendee menu. See [Menu Item](get-booking-attendee-list.md#menu-item) section for details of each item  |

## Menu Item

A menu item is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| sessionId | integer | required | The id of the session to which the booking menu belongs |
| menuId | integer | required | The id of the attendee to which the booking attendee belongs |
| inventoryId | integer | required | The id of the attendee to which the booking attendee belongs |