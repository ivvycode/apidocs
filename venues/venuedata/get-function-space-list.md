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
            "modifiedDate": "2020-12-07 00:20:45 UTC"
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
| id | integer | The unique function space identifier |
| venueId | integer | The id of the venue to which the function space belongs |
| name | string | The name of the function space |
| description | string| The description of the function space |
| categoryId | integer | The category of the space |
| imageId | integer | The main image id of the space |
| hasLayouts | boolean | Whether or not space have layouts |
| minPax | integer | The minimum pax of the space. |
| maxPax | integer | The maximum pax of the space. |
| maxNumBookings | integer | The maximum number of confirmed booking that can share this space at the same time. |
| area | float | The area of the space |
| length | float | The length of the space |
| width | float | The width of the space |
| heightMaximum | float | The maximum height of the space |
| heightMinimum | float | The minimum height of the space |
| floorPressureMaximum | float | The maximum floor pressure of the space |
| partSpaceIds | array | The array of ids of space for smallest individual spaces |
| includedInReportDashboard | boolean | Whether or not this space should be included in the reporting dashboard calculations (e.g. CI revenue per function space). |
| threeDScanId | string | ID which will show 3D view of your space on iVvy |
| useIntegrationPartner | boolean | Whether this function space is integrated with ResDiary |
| isViewable | boolean | Whether or not the space is viewable on the marketplace. |
| marketplaceName | string | The name of the function space shown on the Marketplace. |
| eventTypes | array | The types of events that can be held in the function space. |
| canBeLiveBooked | boolean | Whether or not the function space can be booked live on the Marketplace. |
| canProvideFoodBeverage | boolean | Whether or not food and beverage can be added to the function space. |
| menuTypeIds | array | If space can provide the food and beverage, this will be array of ids of menu types |
| beverageCategoryIds | array | If space can provide the food and beverage, this will be array of ids of beverage types |
| availableFromTime | string | Restrict the earliest start time available for this function space on the marketplace/booking engine. |
| availableTillTime | string | Restrict the latest end time available for this function space on the marketplace/booking engine. |
| minimumBookingTime | integer | This is the minimum number of continuous hours that this function space needs to be free for before it is considered to be available. |
| restrictBookingTimeInterval | integer | Restrict the blocks of time when booking. If 15 mins is chosen then you could not book 9:00-9:20. You would need to book 9:00-9:15 or 9:00-9:30. |
| availableDaysOfWeek | array | The days of the week that this space is bookable. |
| displayAvailabilityTo | integer | Controls whether bookers can see the live availability of this space via a mini-calendar of the day. |
| restrictVisibility | integer | Whether or not the space visibility restricted on marketplace |
| userGroupIds | array | When Restrict Visibility is set to true, these are the groups of users that are allowed to select this space on your venue\'s marketplace booking page. The space will not be visible to anyone not in these groups. |
| isViewableToAnonymousUsers | boolean | When Restrict Visibility is set to true, whether or not to allow make this space visible to anonymous users. The anonymous users are users who are not logged in on your marketplace page. |
| sortOrder | integer | The sorting order number of the space when space is being listed in backend. The sort order used for displaying spaces in order on documents, etc |
| marketplaceSortOrder | integer | The sorting order number of the space for marketplace. The sort order used for displaying space on markteplace/booking engines |
| createdDate | timestamp | The date & time the space was created |
| modifiedDate | timestamp | The date & time the space was last modified |