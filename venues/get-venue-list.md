# Get Venue List

## Description

Get list of venues.

The result from this call will be a [collection](../interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../interpreting-the-response/pagination.md) and [filter](../interpreting-the-response/filtering.md) properties.

## Api Url

`[PlatformAddress]/api/1.0/venue?action=getVenueList`

## Example Response

```javascript
{
  "meta": {
    "totalResults": 19,
    "start": 0,
    "perPage": 2,
    "count": 2
  },
  "results": [
    {
      "id": 21,
      "hashId": "1efda3e35a75aabd13e8996037d35a79",
      "businessName": "iVvy Conference Centre",
      "businessNumber": 1231235,
      "phone": "1300 004 889",
      "fax": "",
      "websiteAddress": "www.ivvy.com",
      "emailAddress": "support@ivvy.com",
      "description": "<p>Located by the River at Hamilton, this is the closest 5.5 star, full service Hotel to the Brisbane Cruise Terminal - Portside at Hamilton, the Airport precinct, Gateway Arterial Bridge linking the Gold Coast to the Sunshine Coast and is just minutes from the CBD.</p>  <p>Featuring 90 spacious, newly refurbished and well appointed accommodation rooms, the hotel is an urban escape perfect for business or leisure travellers alike. Most rooms feature magnificent views of the widest reach of the Brisbane River spanning from the Brisbane City past the Brisbane Cruise Terminal and to the Gateway Bridge.</p>  <p>Enjoy the resort style pool, spa, sauna, gym and complimentary car parking &amp; Wi-Fi for all delegates, guests and visitors.</p>  <p>From the grandeur of the column free Hamilton Ballroom which can easily divide into smaller configurations, the intimacy of the Newstead Room or take advantage of the newly refurbished Executive Boardroom the Brisbane Riverview Hotel has an option to suit your budget and requirements. The resort style pool area is a fantastic venue for breakout sessions or lunches. This is a flexible and well equipped conference venue can cater for intimte boardroom meeting of 6 people up to large corporate events for up to 300 delegates.</p>  <p>With expansive river views, Plates Restaurant offers a seasonal menu showcasing superb produce from Queensland&#8217;s freshest seafood, international cuisine, and wood fired steaks and pizzas. It is the perfect place for business or pleasure, mixing excellent atmosphere with great service.</p> ",
      "checkinTime": "11:00:00",
      "checkoutTime": "14:00:00",
      "childAge": 0,
      "infantAge": 0,
      "currencyCode": "AUD",
      "localeCode": "en_AU",
      "timezone": "Australia/Brisbane",
      "hasSpaces": true,
      "hasAccommodation": true,
      "numMeetingRooms": 20,
      "numAccommodationRooms": 500,
      "maxSpaceArea": null,
      "totalSpaceArea": null,
      "longitude": "153.4086914",
      "latitude": "-28.0793739",
      "primaryAddress": {
        "line1": "1 Bellvue Drive",
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
      "isTaxExclusive": false
    },
    {
      "id": 37,
      "hashId": "5c7264a5dd3525690bb134bd9480ffcd",
      "businessName": "IvVy HQ",
      "businessNumber": 12345789,
      "phone": "1300 399 399",
      "fax": "(+617) 5657 4499",
      "websiteAddress": "",
      "emailAddress": null,
      "description": null,
      "checkinTime": null,
      "checkoutTime": null,
      "childAge": 0,
      "infantAge": 0,
      "currencyCode": "AUD",
      "localeCode": "en_AU",
      "timezone": "Australia/Brisbane",
      "hasSpaces": true,
      "hasAccommodation": true,
      "numMeetingRooms": 0,
      "numAccommodationRooms": 0,
      "maxSpaceArea": null,
      "totalSpaceArea": null,
      "longitude": "153.409881",
      "latitude": "-28.079096",
      "primaryAddress": {
        "line1": "244EZU5W",
        "line2": "55K0CD6Z",
        "line3": "9UQSFQJB",
        "line4": "7UA0P52H",
        "city": "49NE250N",
        "stateCode": "QLD",
        "stateName": null,
        "countryCode": "AU",
        "countryName": null,
        "postalCode": "8CBLZE9Y"
      },
      "isTaxExclusive": false
    }
  ]
}
```

