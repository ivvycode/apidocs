# Get Venue

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getVenue" method="post" summary="Get Venue" %}
{% swagger-description %}
Get the details to a specific venue to which the user has access
{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The venue Id
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}

```
{
    "id": 1,
    "hashId": "925a1e841805031a06e4586828257520",
    "businessName": "Peppers Soul Surfers Paradise Tax Exclusive",
    "businessNumber": "",
    "venueIdentifier": "Identifier",
    "phone": "0123456789",
    "fax": "",
    "websiteAddress": "",
    "emailAddress": "test@email.com",
    "description": "<p>Description</p>\n",
    "checkinTime": null,
    "checkoutTime": null,
    "childAge": 0,
    "infantAge": 0,
    "currencyCode": "AUD",
    "localeCode": "en_AU",
    "timezone": "Pacific/Midway",
    "hasSpaces": true,
    "hasAccommodation": true,
    "numMeetingRooms": 10,
    "numAccommodationRooms": 50,
    "maxSpaceArea": 100,
    "totalSpaceArea": 1000,
    "longitude": "-79.3763095",
    "latitude": "43.6460143",
    "primaryAddress": {
        "line1": "8 The Esplanade",
        "line2": "",
        "line3": "",
        "line4": "",
        "city": "Varsity Lake",
        "stateCode": "QLD",
        "stateName": null,
        "countryCode": "AU",
        "countryName": null,
        "postalCode": "4227"
    },
    "isTaxExclusive": true,
    "hasDistributionChannel": false,
    "allowsLiveBook": true,
    "instantBookUrl": "https://www.ivvy.com.au/venue/order/start?v=925a1e841805031a06e4586828257520",
    "availability": {
        "2024-01-01": {
            "isAvailable": false
        },
        "2024-01-02": {
            "isAvailable": false
        },
        "2024-01-03": {
            "isAvailable": false
        }
    },
    "createdDate": "2017-12-18 12:11:45 UTC",
    "modifiedDate": "2025-04-29 04:11:57 UTC",
    "lastModifiedDate": "2025-04-30 03:57:21 UTC",
    "videoUrls": [
        "asdasd",
        "test"
    ],
    "airportName": "",
    "airportDistance": "11",
    "starRating": 6.5,
    "ratingAuthority": 1,
    "maxSpaceCapacity": 100,
    "facilities": [
        2,
        1,
        3,
        6,
        7,
        9,
        12,
        13,
        15,
        36,
        19
    ],
    "mainImage": {
        "url": "https://s3-ap-southeast-2.amazonaws.com/development.accounts.ivvy.com/account2/venues/1/102482716866e7885c6c38b.jpg",
        "originalFileName": "4258468533.jpg",
        "tags": [],
        "size": 149613,
        "contentType": "image/jpeg"
    },
    "marketplaceBannerImage": null,
    "brochureFile": null,
    "imageLibrary": [],
    "packages": [
        {
            "id": 1,
            "name": "Standard with Accomm",
            "minPax": 1,
            "price": 500,
            "priceMethod": 1,
            "smallDescription": "Standard",
            "largeDescription": "<p>Standard</p>\n",
            "marketplaceName": "Standard",
            "marketplaceEventTypes": null
        },
        {
            "id": 4,
            "name": "Premium",
            "minPax": 1,
            "price": 100,
            "priceMethod": 1,
            "smallDescription": "sdsd",
            "largeDescription": null,
            "marketplaceName": "Premium",
            "marketplaceEventTypes": null
        }
    ],
    "functionSpaces": [
        {
            "id": 3,
            "name": "Space",
            "description": null,
            "area": null,
            "length": null,
            "width": null,
            "heightMaximum": null,
            "heightMinimum": null,
            "floorPressureMaximum": null,
            "marketplaceName": "PRO - The Salon (Space 1)",
            "marketplaceEventTypes": null,
            "minPax": 1,
            "maxPax": 10,
            "hasLayouts": true,
            "image": {
                "url": "https://s3-ap-southeast-2.amazonaws.com/development.accounts.ivvy.com/account2/venues/1/spaces/3/617f6ad3b0bde.png",
                "originalFileName": "standard_decade.png",
                "tags": [],
                "size": 7051,
                "contentType": "image/png"
            },
            "layouts": [
                {
                    "id": 5,
                    "type": 1,
                    "paxMinimum": null,
                    "paxMaximum": null,
                    "timeForSetup": 0,
                    "timeForTakedown": 0
                }
            ]
        }
    ],
    "accommodation": [
        {
            "id": 6,
            "code": "2-6",
            "name": "Ocean King Room (Conference Centre)",
            "description": "<p>room one desc</p>\n",
            "numStandardAdults": 2,
            "numExtraAdults": 1,
            "extraAdultCost": 13,
            "canSmoke": false,
            "capacity": 200,
            "marketplaceName": "Room 1",
            "image": {
                "url": "https://s3-ap-southeast-2.amazonaws.com/development.accounts.ivvy.com/account2/venues/1/accommodation/6/5d92b47f1925e.jpg",
                "originalFileName": "55b97e5479c87.jpg",
                "tags": [],
                "size": 133133,
                "contentType": "image/jpeg"
            }
        }
    ],
    "menus": [
        {
            "id": 1,
            "name": "Lunch",
            "marketplaceName": "Lunch",
            "smallDescription": "Description",
            "menuTypeCategory": 0,
            "image": null,
            "minimumPax": null,
            "maximumPax": null,
            "marketplaceCategories": [
                3
            ],
            "currentStatus": 1,
            "activePeriodStart": {
                "month": 1,
                "date": 2
            },
            "activePeriodEnd": null
        },
        {
            "id": 13,
            "name": "Total of all & items",
            "marketplaceName": "Lunch",
            "smallDescription": "Description",
            "menuTypeCategory": 0,
            "image": null,
            "minimumPax": null,
            "maximumPax": null,
            "marketplaceCategories": [
                3
            ],
            "currentStatus": 1,
            "activePeriodStart": null,
            "activePeriodEnd": null
        }
    ],
    "beveragePackages": [
        {
            "id": 33,
            "name": "Hourly Price - Complimentary house cocktail on arrival",
            "marketplaceName": "Hourly Price",
            "smallDescription": "Morning maza",
            "minPax": 0,
            "maxPax": 0,
            "marketplaceCategories": [
                2
            ],
            "currentStatus": 1,
            "activePeriodStart": null,
            "activePeriodEnd": null
        },
        {
            "id": 7,
            "name": "Per Person - 30 Minute Pre-dinner Beverages",
            "marketplaceName": null,
            "smallDescription": "Per Person",
            "minPax": 0,
            "maxPax": 0,
            "marketplaceCategories": [],
            "currentStatus": 1,
            "activePeriodStart": null,
            "activePeriodEnd": null
        }
    ],
    "reviews": [],
    "accommodationSetting": {
        "enableMultiOccupancy": true
    },
    "cateringWebsitePrimaryColour": "#ae1e1e",
    "cateringWebsiteLogoId": "1819",
    "cateringWebsiteLogo": {
        "id": 1819,
        "accountId": 2,
        "originalFileName": "standard_hour.png",
        "size": 5929,
        "contentType": "image/png",
        "url": "https://s3-ap-southeast-2.amazonaws.com/development.accounts.ivvy.com/account2/venues/1/6180b0108fe0f.png"
    },
    "cateringWebsiteBannerId": "1820",
    "cateringWebsiteBanner": {
        "id": 1820,
        "accountId": 2,
        "originalFileName": "standard_day_meridian.png",
        "size": 7204,
        "contentType": "image/png",
        "url": "https://s3-ap-southeast-2.amazonaws.com/development.accounts.ivvy.com/account2/venues/1/6180b017aea26.png"
    }
}
```

{% endswagger-response %}
{% endswagger %}

## Example Request

`Get a specific venue`

```javascript
{
  "id":21
}
```

## Returns

| Property                     | Type                                                                | Description                                                |
| ---------------------------- | ------------------------------------------------------------------- | ---------------------------------------------------------- |
| id                           | integer                                                             | The unique identifier for the venue.                       |
| hashId                       | string                                                              | The unique hash identifier for the venue.                  |
| businessName                 | string                                                              | The name of the venue.                                     |
| businessNumber               | string                                                              | The business number of the venue.                          |
| venueIdentifier              | string                                                              | Available within reports and API to complement Venue Name. |
| phone                        | string                                                              | The contact phone number of the venue.                     |
| fax                          | string                                                              | The fax number of the venue.                               |
| websiteAddress               | string                                                              | The website address of the venue.                          |
| emailAddress                 | string                                                              | The email address of the venue.                            |
| description                  | string                                                              | The description of the venue.                              |
| checkinTime                  | string                                                              | The check-in time for accommodation.                       |
| checkoutTime                 | string                                                              | The check-out time for accommodation.                      |
| childAge                     | integer                                                             | The age of a child for the venue.                          |
| infantAge                    | integer                                                             | The age of an infant for the venue.                        |
| currencyCode                 | string                                                              | The currency code of the venue.                            |
| localeCode                   | string                                                              | The locale code of the venue.                              |
| timezone                     | string                                                              | The timezone of the venue.                                 |
| hasSpaces                    | boolean                                                             | If the venue has spaces.                                   |
| hasAccommodation             | boolean                                                             | If the venue has accommodation.                            |
| numMeetingRooms              | integer                                                             | The number of meeting rooms in the venue.                  |
| numAccommodationRooms        | integer                                                             | The number of accommodation rooms in the venue.            |
| maxSpaceArea                 | integer                                                             | The maximum area of the largest space in the venue.        |
| totalSpaceArea               | integer                                                             | The total area of all spaces in the venue.                 |
| longitude                    | float                                                               | The longitude of the venue.                                |
| latitude                     | float                                                               | The latitude of the venue.                                 |
| primaryAddress               | object of [Address](get-venue-list.md#address)                      | The primary address of the venue.                          |
| isTaxExclusive               | boolean                                                             | If the venue is tax exclusive.                             |
| hasDistributionChannel       | boolean                                                             | Whether or not the venue has a distribution channel.       |
| allowsLiveBook               | boolean                                                             | If the venue allows live booking.                          |
| instantBookUrl               | string                                                              | The URL for instant booking.                               |
| availability                 | object                                                              | The availability details of the venue.                     |
| createdDate                  | string                                                              | The date when the venue was created.                       |
| modifiedDate                 | string                                                              | The date when the venue was last modified.                 |
| lastModifiedDate             | string                                                              | The date of last modification.                             |
| videoUrls                    | array of string                                                     | The list of video URLs for the venue.                      |
| airportName                  | string                                                              | The name of the nearest airport.                           |
| airportDistance              | string                                                              | The distance from the nearest airport.                     |
| starRating                   | float                                                               | The star rating of the venue.                              |
| ratingAuthority              | integer                                                             | The rating authority of the venue.                         |
| maxSpaceCapacity             | integer                                                             | The maximum space capacity of the venue.                   |
| facilities                   | array of integer                                                    | The list of facility IDs for the venue.                    |
| mainImage                    | object of [file](get-venue.md#file)                                 | The main image details of the venue.                       |
| marketplaceBannerImage       | object of [file](get-venue.md#file)                                 | The marketplace banner image details of the venue.         |
| brochureFile                 | object of [file](get-venue.md#file)                                 | The brochure file details of the venue.                    |
| imageLibrary                 | array of [file](get-venue.md#file)                                  | The list of image library items.                           |
| packages                     | array of [package](get-venue.md#package)                            | The list of venue packages.                                |
| functionSpaces               | array of [functionSpace](get-venue.md#functionspace)                | The list of function spaces.                               |
| accommodation                | array of [accommodation](get-venue.md#accommodation)                | The list of accommodation rooms.                           |
| menus                        | array of [menu](get-venue.md#menu)                                  | The list of menus.                                         |
| beveragePackages             | array of [beveragePackage](get-venue.md#beveragepackage)            | The list of beverage packages.                             |
| reviews                      | array                                                               | The list of reviews.                                       |
| accommodationSetting         | object of [accommodationSetting](get-venue.md#accommodationsetting) | The accommodation settings.                                |
| cateringWebsitePrimaryColour | string                                                              | The primary color for the catering website.                |
| cateringWebsiteLogoId        | integer                                                             | The ID of the catering website logo.                       |
| cateringWebsiteLogo          | object of [file](get-venue.md#file)                                 | The catering website logo details.                         |
| cateringWebsiteBannerId      | integer                                                             | The ID of the catering website banner.                     |
| cateringWebsiteBanner        | object of [file](get-venue.md#file)                                 | The catering website banner details.                       |
| businessNumber               | integer                                                             | The business number of the venue.                          |
| phone                        | string                                                              | The phone number of the venue.                             |
| fax                          | string                                                              | The fax number of the venue.                               |
| websiteAddress               | string                                                              | The website address of the venue.                          |
| emailAddress                 | string                                                              | The email address of the venue.                            |
| description                  | string                                                              | The description of the venue.                              |
| checkinTime                  | string                                                              | The checkin time of the venue.                             |
| checkoutTime                 | string                                                              | The checkout time of the venue.                            |
| childAge                     | integer                                                             | The age of a child for the venue.                          |
| infantAge                    | integer                                                             | The age of an infant for the venue.                        |
| currencyCode                 | string                                                              | The currency code of the venue.                            |
| localeCode                   | string                                                              | The locale code of the venue.                              |
| timezone                     | string                                                              | The timezone of the venue.                                 |
| hasSpaces                    | boolean                                                             | If the venue has spaces.                                   |
| hasAccommodation             | boolean                                                             | If the venue has accommodation.                            |
| numMeetingRooms              | integer                                                             | The number of meeting rooms in the venue.                  |
| numAccommodationRooms        | integer                                                             | The number of accommodation rooms in the venue.            |
| maxSpaceArea                 | integer                                                             | The maximum area of the largest space in the venue.        |
| totalSpaceArea               | integer                                                             | The total area of all spaces in the venue.                 |
| longitude                    | float                                                               | The longitude of the venue.                                |
| latitude                     | float                                                               | The latitude of the venue.                                 |
| primaryAddress               | object of [address](get-venue.md#address)                           | The primary address of the venue.                          |
| isTaxExclusive               | boolean                                                             | If the venue is tax exclusive.                             |

## address

| Property    | Type   | Description                      |
| ----------- | ------ | -------------------------------- |
| line1       | string | The first line of the address.   |
| line2       | string | The second line of the address.  |
| line3       | string | The third line of the address.   |
| line4       | string | The fourth line of the address.  |
| city        | string | The city of the address.         |
| stateCode   | string | The state code of the address.   |
| stateName   | string | The state name of the address.   |
| countryCode | string | The country code of the address. |
| countryName | string | The country name of the address. |
| postalCode  | string | The postal code of the address.  |

## package

| Property              | Type    | Description                                   |
| --------------------- | ------- | --------------------------------------------- |
| id                    | integer | The unique identifier for the package.        |
| name                  | string  | The name of the package.                      |
| minPax                | integer | The minimum number of people for the package. |
| price                 | float   | The price of the package.                     |
| priceMethod           | integer | The price method for the package.             |
| smallDescription      | string  | The small description of the package.         |
| largeDescription      | string  | The large description of the package.         |
| marketplaceName       | string  | The marketplace name of the package.          |
| marketplaceEventTypes | array   | The event types of the package.               |

## functionSpace

| Property             | Type                                   | Description                                                                                |
| -------------------- | -------------------------------------- | ------------------------------------------------------------------------------------------ |
| id                   | integer                                | The unique identifier for the function space.                                              |
| name                 | string                                 | The name of the function space.                                                            |
| description          | string                                 | The description of the function space.                                                     |
| area                 | integer                                | The area of the function space.                                                            |
| length               | float                                  | The length of the function space.                                                          |
| width                | float                                  | The width of the function space.                                                           |
| heightMaximum        | float                                  | The maximum height of the function space.                                                  |
| heightMinimum        | float                                  | The minimum height of the function space.                                                  |
| floorPressureMaximum | float                                  | The maximum floor pressure of the function space.                                          |
| floorPressureMinimum | float                                  | The minimum floor pressure of the function space.                                          |
| marketplaceName      | string                                 | The marketplace name of the function space.                                                |
| minPax               | integer                                | The minimum number of people allowed within a single session to order this function space. |
| maxPax               | integer                                | The maximum number of people allowed within a single session to order this function space. |
| hasLayouts           | boolean                                | If the function space has layouts.                                                         |
| image                | object of [file](get-venue.md#file)    | The image of the function space.                                                           |
| layouts              | array of [layout](get-venue.md#layout) | The list of layouts for the function space.                                                |

## layout

| Property        | Type                                | Description                                                                                                                                               |
| --------------- | ----------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id              | integer                             | The unique identifier for the layout.                                                                                                                     |
| type            | integer                             | The type of the layout. 1 = Theatre, 2 = Classroom, 3 = U-Shape, 4 = Cabaret, 5 = Boardroom, 6 = Banquet, 7 = Cocktail, 8 = Hollow Square, 9 = Exhibition |
| name            | string                              | The name of the layout.                                                                                                                                   |
| description     | string                              | The description of the layout.                                                                                                                            |
| image           | object of [file](get-venue.md#file) | The image of the layout.                                                                                                                                  |
| paxMinimum      | integer                             | The minimum number of people allowed for the layout.                                                                                                      |
| paxMaximum      | integer                             | The maximum number of people allowed for the layout.                                                                                                      |
| timeForSetup    | integer                             | The time for setup of the layout.                                                                                                                         |
| timeForTakedown | integer                             | The time for takedown of the layout.                                                                                                                      |

## file

| Property         | Type    | Description                   |
| ---------------- | ------- | ----------------------------- |
| url              | string  | The url of the file.          |
| originalFileName | string  | The original file name.       |
| tags             | array   | The tags of the file.         |
| size             | integer | The size of the file.         |
| contentType      | string  | The content type of the file. |

## accommodation

| Property          | Type                                | Description                                         |
| ----------------- | ----------------------------------- | --------------------------------------------------- |
| id                | integer                             | The unique identifier for the accommodation.        |
| code              | string                              | The code of the accommodation.                      |
| name              | string                              | The name of the accommodation.                      |
| description       | string                              | The description of the accommodation.               |
| numStandardAdults | integer                             | The number of standard adults in the accommodation. |
| numExtraAdults    | integer                             | The number of extra adults in the accommodation.    |
| extraAdultCost    | float                               | The cost of an extra adult in the accommodation.    |
| canSmoke          | boolean                             | If smoking is allowed in the accommodation.         |
| capacity          | integer                             | The capacity of the accommodation.                  |
| marketplaceName   | string                              | The marketplace name of the accommodation.          |
| image             | object of [file](get-venue.md#file) | The image of the accommodation.                     |

## menu

| Property              | Type                                                | Description                                |
| --------------------- | --------------------------------------------------- | ------------------------------------------ |
| id                    | integer                                             | The unique identifier for the menu.        |
| name                  | string                                              | The name of the menu.                      |
| marketplaceName       | string                                              | The marketplace name of the menu.          |
| smallDescription      | string                                              | The small description of the menu.         |
| menuTypeCategory      | integer                                             | The category of the menu type.             |
| image                 | object of [file](get-venue.md#file)                 | The image of the menu.                     |
| minimumPax            | integer                                             | The minimum number of people for the menu. |
| maximumPax            | integer                                             | The maximum number of people for the menu. |
| marketplaceCategories | array                                               | The categories of the menu.                |
| currentStatus         | integer                                             | The status of the menu.                    |
| activePeriodStart     | object of [activePeriod](get-venue.md#activeperiod) | The start period when the menu is active.  |
| activePeriodEnd       | object of [activePeriod](get-venue.md#activeperiod) | The end period when the menu is active.    |

## activePeriod

| Property | Type    | Description              |
| -------- | ------- | ------------------------ |
| month    | integer | The month of the period. |
| date     | integer | The date of the period.  |

## beveragePackage

| Property | Type | Description |
| Property | Type | Description |
| --------------------- | -------- | ----------------------------------------------------------------------------------------------- |
| id | integer | The unique identifier for the beverage package. |
| name | string | The name of the beverage package. |
| marketplaceName | string | The marketplace name of the beverage package. |
| smallDescription | string | The small description of the beverage package. |
| minimumPax | integer | The minimum number of people for the beverage package. |
| maximumPax | integer | The maximum number of people for the beverage package. |
| marketplaceCategories | array | The categories of the beverage package. |
| currentStatus | integer | The status of the beverage package. |
| activePeriodStart | object of [activePeriod](get-venue.md#activeperiod) | The start period when the beverage package is active. |
| activePeriodEnd | object of [activePeriod](get-venue.md#activeperiod) | The end period when the beverage package is active. |

## accommodationSetting

| Property             | Type    | Description                                             |
| -------------------- | ------- | ------------------------------------------------------- |
| enableMultiOccupancy | boolean | If the accommodation setting allows multiple occupancy. |

## ratingAuthority

One of the following values:

- 1 = AAA rated
- 2 = Self rated

## facilities

An array of the following values:

- 1 = Air Conditioning
- 2 = Airport Shuttle
- 3 = Audio Visual
- 4 = BBQ
- 6 = Business Centre
- 7 = Ceremony On Site
- 8 = Child Minding
- 9 = Disabled Access
- 10 = Dry Cleaning
- 11 = Express Checkout
- 12 = Free Parking
- 13 = Gaming Area
- 14 = Gymnasium
- 15 = Internet Access
- 16 = Laundry
- 39 = Liquor License
- 17 = Mobile Bar
- 18 = Open 24 Hours
- 19 = Outdoor Area
- 20 = Parking Available
- 21 = Pay TV
- 22 = Playground
- 23 = Printing Services
- 24 = Public Transport
- 25 = Restaurant On Site
- 26 = Sauna Steam Room
- 27 = Smoking Permitted
- 28 = Spa
- 29 = Staging
- 30 = Street Parking
- 31 = Swimming Pool
- 32 = Tour Desk
- 33 = Undercover Parking
- 34 = Valet Parking
- 35 = Wheelchair Access
- 36 = Wifi Access
- 37 = Outside Catering Allowed
- 38 = BYO Allowed

## priceMethod (package pricing)

One of the following values:

- 1 = Per person
- 2 = Flat rate

## type (function space layout)

One of the following values:

- 0 = Custom
- 1 = Theatre
- 2 = Classroom
- 3 = U-Shape
- 4 = Cabaret
- 5 = Boardroom
- 6 = Banquet
- 7 = Cocktail
- 8 = Hollow Square

## marketplaceEventTypes

Packages, function spaces and image library file for the marketplaceEventType.

An array of the following values:

- 11 = Event
- 21 = Wedding
- 31 = Conference
- 41 = Meeting
