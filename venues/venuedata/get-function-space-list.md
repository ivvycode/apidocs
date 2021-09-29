# Get Function Space List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getFunctionSpaceList" path="" %}
{% api-method-summary %}
Get Venue Function Space List
{% endapi-method-summary %}

{% api-method-description %}
Return the venue function spaces list for the venue.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 1,
        "start": 0,
        "perPage": 100,
        "count": 1
    },
    "results": [
        {
            "id": 1,
            "venueId": 1,
            "name": "Some Space",
            "description": "<p>This is some space</p> ",
            "categoryId": 1,
            "imageId": 2555,
            "hasLayouts": true,
            "minPax": 1,
            "maxPax": 1000,
            "maxNumBookings": 1,
            "area": 100,
            "length": 100,
            "width": 100,
            "heightMaximum": 15,
            "heightMinimum": 15,
            "floorPressureMaximum": 100,
            "partSpaceIds": [],
            "includedInReportDashboard": true,
            "threeDScanId": "",
            "useIntegrationPartner": false,
            "isViewable": true,
            "marketplaceName": "Some Space",
            "eventTypes": [
                1,
                2,
                14,
                15,
                16,
                17,
                18
            ],
            "canBeLiveBooked": true,
            "canProvideFoodBeverage": true,
            "menuTypeIds": [
                1,
                2,
                4
            ],
            "beverageCategoryIds": [
                1,
                2,
                3,
                4,
                6
            ],
            "availableFromTime": null,
            "availableTillTime": null,
            "minimumBookingTime": null,
            "restrictBookingTimeInterval": null,
            "availableDaysOfWeek": [],
            "displayAvailabilityTo": null,
            "restrictVisibility": null,
            "userGroupIds": [],
            "isViewableToAnonymousUsers": true,
            "sortOrder": 3,
            "marketplaceSortOrder": 1,
            "createdDate": "2015-01-09 03:51:23 UTC",
            "modifiedDate": "2020-12-07 00:20:45 UTC",
            "layouts": [
                {
                    "id": 1,
                    "layoutName": "Theatre"
                },
                {
                    "id": 2,
                    "layoutName": "Cabaret"
                }
            ]
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get Venues Function Space List`

```javascript
{
  "venueId": 1
}
```

## Returns

`A collection object with the following properties in the results`

| Property | Data Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the space. |
| venueId | integer | The id of the venue to which the space belongs. |
| name | string | The name of the space. |
| description | string | The description of the space. |
| categoryId | integer | The id of the category assigned to the space. |
| imageId | integer | The id of the main image the space. |
| hasLayouts | boolean | Whether or not the space has layouts. |
| minPax | integer | The minimum pax of the space. |
| maxPax | integer | The maximum pax of the space. |
| maxNumBookings | integer | The maximum number of confirmed bookings that can share this space at the same time. |
| area | float | The area of the space. |
| length | float | The length of the space. |
| width | float | The width of the space. |
| heightMaximum | float | The maximum height of the space. |
| heightMinimum | float | The minimum height of the space. |
| floorPressureMaximum | float | The maximum floor pressure of the space. |
| partSpaceIds | array | The ids of the spaces that are the smallest spaces that divide this space. |
| includedInReportDashboard | boolean | Whether or not this space should be included in the reporting dashboard calculations \(e.g. CI revenue per space\). |
| threeDScanId | string | An ID which can be used to display a 3D view of the space. |
| useIntegrationPartner | boolean | Whether or not the space is integrated with ResDiary. |
| isViewable | boolean | Whether or not the space is viewable on the iVvy marketplace and booking engines. |
| marketplaceName | string | The name of the space shown on the iVvy marketplace and booking engines. |
| eventTypes | array | The types of events that can be held in the space. |
| canBeLiveBooked | boolean | Whether or not the space can be booked live on the iVvy marketplace and booking engines. |
| canProvideFoodBeverage | boolean | Whether or not food and beverage can be added to the space. |
| menuTypeIds | array | The ids of the types of menus available if the space can provide food and beverage. |
| beverageCategoryIds | array | The ids of the types of beverage packages available if the space can provide food and beverage. |
| availableFromTime | string | The earliest time from which the space can be reserved on the iVvy marketplace and booking engines. |
| availableTillTime | string | The latest time to which the space can be reserved on the iVvy marketplace and booking engines. |
| minimumBookingTime | integer | The minimum number of continuous hours that must not be reserved for the space to be considered available for reservations. |
| restrictBookingTimeInterval | integer | The smallest minute block interval for which the space can be reserved. For example, if 15 minutes then reservations from 0900 to 0920 are not allowed, but reservations from 0900 to 0915, 0900 to 0930, 0900 to 0945 etc. are allowed. |
| availableDaysOfWeek | array | The days of the week that the space is available for reservations. |
| displayAvailabilityTo | integer | Controls whether or not meeting bookers can see the live availability of the space via a mini-calendar of the day. |
| restrictVisibility | integer | Whether or not the space visibility is restricted on the iVvy marketplace and booking engines. |
| userGroupIds | array | The ids of the groups of users allowed to reserve the space on the venue's marketplace booking page when "restrictVisibility" is true. |
| isViewableToAnonymousUsers | boolean | Whether or not annonymous users are allowed to reserve the space on the venue's marketplace booking page when "restrictVisibility" is true. |
| sortOrder | integer | The sorting order of the space. Used to sort the list of spaces in documents etc. |
| marketplaceSortOrder | integer | The sorting order of the space on the iVvy marketplace and booking engines. |
| createdDate | timestamp | The date & time the space was created. |
| modifiedDate | timestamp | The date & time the space was last modified. |
| layouts | array | Collection of layouts tied to the requested space |

