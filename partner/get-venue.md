# Get Venue

{% api-method method="post" host="\[PlatformAddress\]" path="/api/1.0/partner?action=getVenue" %}
{% api-method-summary %}
Get Venue
{% endapi-method-summary %}

{% api-method-description %}
This endpoint fetches the public details of a specific venue in the iVvy marketplace. The unique id of the venue is required.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The unique identifier of the venue
{% endapi-method-parameter %}

{% api-method-parameter name="availabilityStartDate" type="string" required=false %}
The start date of the period from which to include the function space availability details of the venues
{% endapi-method-parameter %}

{% api-method-parameter name="availabilityEndDate" type="string" required=false %}
The end date of the period from which to include the function space availability details of the venues
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
  "id": 21,
  "hashId": "1efda3e35a75aabd13e8996037d35a79",
  "businessName": "iVvy Conference Centre",
  "businessNumber": 123123,
  "phone": "1300 004 889",
  "fax": "",
  "websiteAddress": "",
  "emailAddress": "example@domain.com",
  "description": "<p>Located by the River at Hamilton, this is the closest 5 star, full service Hotel to the Brisbane Cruise Terminal - Portside at Hamilton, the Airport precinct, Gateway Arterial Bridge linking the Gold Coast to the Sunshine Coast and is just minutes from the CBD.<br /><br />  Featuring 90 spacious, newly refurbished and well appointed accommodation rooms, the hotel is an urban escape perfect for business or leisure travellers alike. Most rooms feature magnificent views of the widest reach of the Brisbane River spanning from the Brisbane City past the Brisbane Cruise Terminal and to the Gateway Bridge.<br /><br />  Enjoy the resort style pool, spa, sauna, gym and complimentary car parking &amp; Wi-Fi for all delegates, guests and visitors.<br /><br />  From the grandeur of the column free Hamilton Ballroom which can easily divide into smaller configurations, the intimacy of the Newstead Room or take advantage of the newly refurbished Executive Boardroom the Brisbane Riverview Hotel has an option to suit your budget and requirements. The resort style pool area is a fantastic venue for breakout sessions or lunches. This is a flexible and well equipped conference venue can cater for intimte boardroom meeting of 6 people up to large corporate events for up to 300 delegates. <br /><br />  With expansive river views, Plates Restaurant offers a seasonal menu showcasing superb produce from Queensland&#8217;s freshest seafood, international cuisine, and wood fired steaks and pizzas. It is the perfect place for business or pleasure, mixing excellent atmosphere with great service.</p> ",
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
  "longitude": "153.4065773",
  "latitude": "-28.0067947",
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
  "instantBookUrl": "https://www.ivvy.com/order/start?v=1efda3e35a75aabd13e8996037d35a79",
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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



