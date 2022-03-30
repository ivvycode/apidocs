# Get Booking Session Menu List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getBookingSessionList" method="post" summary="Get Booking Session Menu List" %}
{% swagger-description %}
Get a list of booking session menus.
{% endswagger-description %}


{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the bookings belongs
{% endswagger-parameter %}

{% swagger-parameter name="bookingId" type="integer" in="path" %}
The unique id of the booking to which the session belongs
{% endswagger-parameter %}

{% swagger-parameter name="sessionId" type="integer" in="path" %}
The unique id of the session to which the menu belongs
{% endswagger-parameter %}

{% swagger-parameter name="orderBy" type="string" in="request" %}
Order the response by column
{% endswagger-parameter %}

{% swagger-parameter name="orderDir" type="string" in="spec" %}
Order direction the reponse by column
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="path" %}
The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.)
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of bookings session to get in a single call
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 100,
        "count": 1
    },
    "results": [
        {
            "id": "495",
            "venueId": "1",
            "bookingId": "313",
            "sessionId": "519",
            "menuId": "15",
            "menuVenueId": "1",
            "name": "Session menu of items",
            "minAttendeesGuaranteed": 10,
            "sameAsSessionTime": false,
            "startTime": null,
            "endTime": null,
            "includeInPackage": false,
            "bookingPackageId": null,
            "costcenterId": 1,
            "cost": 18,
            "excludedTaxIds": [],
            "items": [
                {
                    "_type": "item",
                    "id": 58,
                    "name": "menu item 1",
                    "description": "",
                    "quantity": 2,
                    "price": 2,
                    "itemCost": 2,
                    "isOptional": 0,
                    "servingTime": null
                },
                {
                    "_type": "item",
                    "id": 59,
                    "name": "menu item 2",
                    "description": "",
                    "quantity": 3,
                    "price": 2,
                    "itemCost": 2,
                    "isOptional": 1,
                    "servingTime": null
                },
                {
                    "_type": "item",
                    "id": 60,
                    "name": "menu item 3",
                    "description": "",
                    "quantity": 4,
                    "price": 2,
                    "itemCost": 2,
                    "isOptional": 1,
                    "servingTime": null
                }
            ],
            "sortOrder": 2,
            "createdDate": "2022-03-24 06:11:07 UTC",
            "modifiedDate": "2022-03-28 00:48:01 UTC",
            "_translations_": {
                "da_DK": {
                    "name": ""
                },
                "de_DE": {
                    "name": ""
                },
                "en_GB": {
                    "name": ""
                },
                "en_US": {
                    "name": "menu of items"
                },
                "es_ES": {
                    "name": ""
                },
                "fr_FR": {
                    "name": ""
                },
                "ms_MY": {
                    "name": ""
                },
                "nl_NL": {
                    "name": ""
                },
                "th_TH": {
                    "name": ""
                }
            }
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md)  of booking session menu to which the user has access. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

`Get a specific venue’s Booking Session List`

```javascript
{
    "perPage" : 100,
    "venueId" : 1,
    "bookingId" : 313
}
```

## Booking Session Menu

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| id | string | optional | The unique id of the booking session menu to update |
| venueId | string | required | The unique id of the venue to which the booking session menu belongs  |
| bookingId | string | required | The unique id of the booking to which the booking session menu belongs  |
| sessionId | string | optional | The unique id of the session to which the booking session menu belongs  | 
| menuId | string | optional | The menu id from venue setup  |
| menuVenueId | string | optional | The unique id of venue to which menu belongs |
| name | mixed | optional | The name of the booking session menu |
| minAttendeesGuaranteed | mixed | optional | The total attendees of the booking session menu |
| sameAsSessionTime | boolean | optional | Whether or not to make start time based on session |
| startTime | string | optional | The start time of the booking session menu |
| endTime | string | optional | The end time of the booking session menu |
| includeInPackage | boolean | optional | Whether or not the menu is included in the package |
| bookingPackageId | integer | optional | The booking package id in which the booking session menu is included. Required when includeInPackage is true |
| costcenterId | integer | optional | The cost center id to which the booking session menu belongs |
| cost | number | optional | The cost of the booking session menu |
| excludedTaxIds | array of integers | optional | The excluded cost tax ids applied to the price of the booking session menu |
| items | array | optional | The items data of the session menu. See [Menu Item](get-booking-session-menu-list.md#group-menu-item) or [Group Menu  Items](get-booking-session-menu-list.md#group-menu-item) section for details of each item |
| sortOrder | integer | optional | The sort order of the booking session menu |
| createdDate | string | optional | The date and time when the session menu was created |
| modifiedDate | string  | optional | The date and time when the session menu was last modified |
| \_translations\_ | mixed | optional | The translations data of the session menu |

## Menu Item

A menu item is an object with the following details.

| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| _type | string | optional |  The type of an session menu item | 
| id | integer | required | The unique id of the booking session menu item | 
| name | string | optional | The name of the booking session menu item | 
| description | string | optional |  The description of the booking session menu item | 
| quantity | integer | optional | The quantity of the booking session menu item | 
| price | double | optional | The price of the booking session menu item | 
| itemCost | double | optional |The cost of the booking session menu item | 
| isOptional | boolean | optional |  Whether or not booking session menu item | 
| servingTime | string | optional | The serving time of the booking session menu item | 


## Group Menu Item
| Property | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| _type | string | optional | The type of an session menu item group | 
| id | string | optional | The unique id of the booking session menu item group | 
| name | string | optional | The name of the booking session menu item group | 
| marketplaceName | string | | optional |The name of the booking session menu item group | 
| minSelection | integer | | optional | The max selection of the booking session menu item group | 
| maxSelection | integer | optional | The min selection of the booking session menu item group | 
| servingTime | string | optional | The serving time of the booking session menu item | 
| items | array | optional | The items data of the session menu group. See [Menu Item](get-booking-session-menu-list.md#group-menu-item) section for details of each item |  
