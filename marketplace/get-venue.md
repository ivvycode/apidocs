# Get Venue

### Description

The result from this call will be the public details of a specific venue in the iVvy marketplace. The unique venue hash identifier is required, for example { "hashId": "abcdefghijklmnop" }

This call also accepts the availabilityStartDate and availabilityEndDate parameters that are described by getVenueList. The behaviour is the same as getVenueList, but for only for the specific venue.

`Example: Get a specific venue and it’s availability from 1st July 2015 to 7th July 2015`

### Api Url

`[PlatformAddress]/api/1.0/venue?action=getVenue`

### Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |


### Example Request

```javascript
{
  "hashId": "1efda3e35a75aabd13e8996037d35a79",
  "availabilityStartDate": "2015-07-01",
  "availabilityEndDate": "2015-07-07"
}
```

### Example Response

```javascript
{
  "id": 21,
  "hashId": "1efda3e35a75aabd13e8996037d35a79",
  "businessName": "iVvy Conference Centre",
  "businessNumber": 123123,
  "phone": "1300 004 889",
  "fax": "",
  "websiteAddress": "",
  "emailAddress": "james.greig@ivvy.com",
  "description": "<p>  Located by the River at Hamilton, this is the closest 5 star, full service Hotel to the Brisbane Cruise Terminal - Portside at Hamilton, the Airport precinct, Gateway Arterial Bridge linking the Gold Coast to the Sunshine Coast and is just minutes from the CBD.<br /><br />  Featuring 90 spacious, newly refurbished and well appointed accommodation rooms, the hotel is an urban escape perfect for business or leisure travellers alike. Most rooms feature magnificent views of the widest reach of the Brisbane River spanning from the Brisbane City past the Brisbane Cruise Terminal and to the Gateway Bridge.<br /><br />  Enjoy the resort style pool, spa, sauna, gym and complimentary car parking &amp; Wi-Fi for all delegates, guests and visitors.<br /><br />  From the grandeur of the column free Hamilton Ballroom which can easily divide into smaller configurations, the intimacy of the Newstead Room or take advantage of the newly refurbished Executive Boardroom the Brisbane Riverview Hotel has an option to suit your budget and requirements. The resort style pool area is a fantastic venue for breakout sessions or lunches. This is a flexible and well equipped conference venue can cater for intimte boardroom meeting of 6 people up to large corporate events for up to 300 delegates. <br /><br />  With expansive river views, Plates Restaurant offers a seasonal menu showcasing superb produce from Queensland&#8217;s freshest seafood, international cuisine, and wood fired steaks and pizzas. It is the perfect place for business or pleasure, mixing excellent atmosphere with great service.</p> ",
  "checkinTime": "11:00:00",
  "checkoutTime": "14:00:00",
  "childAge": 0,
  "infantAge": 0,
  "currencyCode": "AUD",
  "localeCode": "en_AU",
  "timezone": "Australia/Brisbane",
  "hasSpaces": true,
  "hasAccommodation": true,
  "numMeetingRooms": 0,
  "numAccommodationRooms": 200,
  "maxSpaceArea": null,
  "totalSpaceArea": null,
  "longitude": 153.4065773,
  "latitude": -28.0067947,
  "primaryAddress": {
    "line1": "2 Boston Court",
    "line2": "",
    "line3": "",
    "line4": "",
    "city": "Varsity Lakes",
    "stateCode": "QLD",
    "stateName": null,
    "countryCode": "AU",
    "countryName": null,
    "postalCode": 4227
  },
  "instantBookUrl": "http://stagemarketplace.ivvy.com/order/start?v=1efda3e35a75aabd13e8996037d35a79",
  "availability": {
    "2015-07-01": {
      "isAvailable": true
    },
    "2015-07-02": {
      "isAvailable": true
    },
    "2015-07-03": {
      "isAvailable": true
    },
    "2015-07-04": {
      "isAvailable": true
    },
    "2015-07-05": {
      "isAvailable": true
    },
    "2015-07-06": {
      "isAvailable": true
    },
    "2015-07-07": {
      "isAvailable": true
    }
  },
  "videoUrls": [
    "https://www.youtube.com/embed/rxiPVWurK7Q"
  ],
  "airportName": "Gold Coast (OOL)",
  "airportDistance": 20,
  "starRating": 5,
  "ratingAuthority": 2,
  "maxSpaceCapacity": 100,
  "facilities": [
    2,
    3,
    6,
    12,
    14,
    19,
    20,
    24,
    27,
    30,
    31,
    34,
    35
  ],
  "mainImage": {
    "url": "https://s3-ap-southeast-2.amazonaws.com/ap-southeast-2.accounts.ivvy.com/account14/venues/21/55403b462c0aa.jpg",
    "originalFileName": "main function sapce 2.jpg",
    "tags": [],
    "size": 2647159,
    "contentType": "image/jpeg"
  },
  "marketplaceBannerImage": {
    "url": "https://s3-ap-southeast-2.amazonaws.com/ap-southeast-2.accounts.ivvy.com/account14/venues/21/banner/banner.jpg",
    "originalFileName": "banner.jpg",
    "tags": [],
    "size": 2963936,
    "contentType": "image/jpeg"
  },
  "brochureFile": null,
  "imageLibrary": [
    {
      "url": "https://s3-ap-southeast-2.amazonaws.com/ap-southeast-2.accounts.ivvy.com/account14/imageLibrary/5513b498229a6.jpg",
      "originalFileName": "58443-room-types-5-vibe-hotel-sydney-executive-king.jpg",
      "tags": [
        "General"
      ],
      "size": 46333,
      "contentType": "image/jpeg",
      "marketplaceEventTypes": [
        21
      ]
    }
  ],
  "packages": [
    {
      "marketplaceName": "Day Delegate Package",
      "marketplaceEventTypes": [
        11,
        21
      ],
      "minPax": 30,
      "price": 98,
      "priceMethod": 1,
      "smallDescription": "At iVvy Conference Centre, intimate spaces are combined with state-of-the-art technology and award-winning food. Our Day Delegate Package is ideal for small to medium meetings or events, offering a range of menus for your attendees",
      "largeDescription": "<p>  At iVvy Conference Centre, intimate spaces are combined with state-of-the-art technology and award-winning food. Our Day Delegate Package is ideal for small to medium meetings or events, offering a range of menus designed by our team of chefs to create a unique dining experience for your attendees.</p> <p>  At just $98 per person, our Day Delegate Package includes the following:</p> <ul><li>   Venue hire</li>  <li>   Pre-installed technical equipment and services including&#160;a high definition projector or display, a PA system and a&#160;presentation computer</li>  <li>   Free Wi-Fi</li>  <li>   Notepads and pens</li>  <li>   Iced water and sweets</li>  <li>   Tea and coffee on arrival</li>  <li>   Morning tea</li>  <li>   Networking lunch</li>  <li>   Afternoon tea.</li> </ul>"
    }
  ],
  "functionSpaces": [
    {
      "marketplaceName": "River Room",
      "marketplaceEventTypes": [
        11,
        21
      ],
      "description": "<p>  Ocean and river views are a focal point of the River room. This room has floor-to-ceiling glass with full length curtains if required, and access to a large, central area for meet-and-greets or pre-dinner cocktails. The large projector screen is perfect for meetings or special events and this room has been fully soundproofed for privacy.</p> ",
      "area": null,
      "length": null,
      "width": null,
      "heightMaximum": null,
      "heightMinimum": null,
      "floorPressureMaximum": null,
      "minPax": 30,
      "maxPax": 400,
      "hasLayouts": true,
      "image": {
        "url": "https://s3-ap-southeast-2.amazonaws.com/ap-southeast-2.accounts.ivvy.com/account14/venues/21/spaces/169/5540362637d5f.jpg",
        "originalFileName": "River Room.jpg",
        "tags": [],
        "size": 67933,
        "contentType": "image/jpeg"
      },
      "layouts": [
        {
          "type": 7,
          "paxMinimum": null,
          "paxMaximum": 400,
          "timeForSetup": null,
          "timeForTakedown": null
        },
        {
          "type": 6,
          "paxMinimum": null,
          "paxMaximum": 150,
          "timeForSetup": null,
          "timeForTakedown": null
        },
        {
          "type": 1,
          "paxMinimum": null,
          "paxMaximum": 250,
          "timeForSetup": null,
          "timeForTakedown": null
        },
        {
          "type": 5,
          "paxMinimum": null,
          "paxMaximum": 80,
          "timeForSetup": null,
          "timeForTakedown": null
        },
        {
          "type": 8,
          "paxMinimum": null,
          "paxMaximum": 50,
          "timeForSetup": null,
          "timeForTakedown": null
        },
        {
          "type": 4,
          "paxMinimum": null,
          "paxMaximum": 100,
          "timeForSetup": null,
          "timeForTakedown": null
        },
        {
          "type": 3,
          "paxMinimum": null,
          "paxMaximum": 100,
          "timeForSetup": null,
          "timeForTakedown": null
        }
      ]
    }
  ],
  "accommodation": [
    {
      "code": "14-53",
      "marketplaceName": "Studio",
      "description": "<ul><li>   A studio apartment sleeps 1-5 and contains a queen bed plus a sofa that can folded out to a double bed.</li>  <li>   Rollaways also available.</li> </ul>",
      "numStandardAdults": 1,
      "numExtraAdults": 1,
      "extraAdultCost": 0,
      "canSmoke": false,
      "capacity": 20,
      "image": {
        "url": "https://s3-ap-southeast-2.amazonaws.com/ap-southeast-2.accounts.ivvy.com/account14/venues/21/accommodation/53/5540352c9c2ca.jpg",
        "originalFileName": "Studio.jpg",
        "tags": [],
        "size": 48330,
        "contentType": "image/jpeg"
      }
    }
  ]
}
```

The following are properties in the example json response above that have special values.

### ratingAuthority

One of the following values:

* 1 = AAA rated
* 2 = Self rated

### facilities

An array of the following values:

* 1 = Air Conditioning
* 2 = Airport Shuttle
* 3 = Audio Visual
* 4 = BBQ
* 6 = Business Centre
* 7 = Ceremony On Site
* 8 = Child Minding
* 9 = Disabled Access
* 10 = Dry Cleaning
* 11 = Express Checkout
* 12 = Free Parking
* 13 = Gaming Area
* 14 = Gymnasium
* 15 = Internet Access
* 16 = Laundry
* 39 = Liquor License
* 17 = Mobile Bar
* 18 = Open 24 Hours
* 19 = Outdoor Area
* 20 = Parking Available
* 21 = Pay TV
* 22 = Playground
* 23 = Printing Services
* 24 = Public Transport
* 25 = Restaurant On Site
* 26 = Sauna Steam Room
* 27 = Smoking Permitted
* 28 = Spa
* 29 = Staging
* 30 = Street Parking
* 31 = Swimming Pool
* 32 = Tour Desk
* 33 = Undercover Parking
* 34 = Valet Parking
* 35 = Wheelchair Access
* 36 = Wifi Access
* 37 = Outside Catering Allowed
* 38 = BYO Allowed

### priceMethod \(package pricing\)

One of the following values:

* 1 = Per person
* 2 = Flat rate

### type \(function space layout\)

One of the following values:

* 0 = Custom
* 1 = Theatre
* 2 = Classroom
* 3 = U-Shape
* 4 = Cabaret
* 5 = Boardroom
* 6 = Banquet
* 7 = Cocktail
* 8 = Hollow Square

### marketplaceEventTypes \(packages, function spaces and image library files\)

An array of the following values:

* 11 = Event
* 21 = Wedding
* 31 = Conference
* 41 = Meeting

