# Get Venue List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="venue?action=getVenueList" %}
{% api-method-summary %}
Get Venue List
{% endapi-method-summary %}

{% api-method-description %}
Get a list of venues.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
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
      "venueIdentifier": "Identifier",
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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Returns

`A collection object with the following properties in the results`

| Property      | Type    | Description                                                                            |
| ---           | ---     | ---                                                                                    |
| id            | integer | The unique identifier for the venue.                                                   |
| hashId        | string  | The unique hash identifier for the venue.                                              |
| businessName  | string  | The name of the venue.                                                                 |
| businessNumber| integer | The business number of the venue.                                                      |
| venueIdentifier| string  | Available within reports and API to complement Venue Name.                            |
| phone         | string  | The phone number of the venue.                                                         |
| fax           | string  | The fax number of the venue.                                                           |
| websiteAddress| string  | The website address of the venue.                                                      |
| emailAddress  | string  | The email address of the venue.                                                        |
| description   | string  | The description of the venue.                                                          |
| checkinTime   | string  | The checkin time of the venue.                                                         |
| checkoutTime  | string  | The checkout time of the venue.                                                        |
| childAge      | integer | The age of a child for the venue.                                                      |
| infantAge     | integer | The age of an infant for the venue.                                                    |
| currencyCode  | string  | The currency code of the venue.                                                        |
| localeCode    | string  | The locale code of the venue.                                                          |
| timezone      | string  | The timezone of the venue.                                                            |
| hasSpaces     | boolean | If the venue has spaces.                                                              |
| hasAccommodation| boolean | If the venue has accommodation.                                                       |
| numMeetingRooms| integer | The number of meeting rooms in the venue.                                              |
| numAccommodationRooms| integer | The number of accommodation rooms in the venue.                                    |
| maxSpaceArea  | integer | The maximum area of the largest space in the venue.                                      |
| totalSpaceArea| integer | The total area of all spaces in the venue.                                               |
| longitude     | float   | The longitude of the venue.                                                            |
| latitude      | float   | The latitude of the venue.                                                             |
| primaryAddress| object of [Address](get-venue-list.md#address)  | The primary address of the venue.   |
| isTaxExclusive| boolean | If the venue is tax exclusive.                                                         |


## Address

| Property      | Type    | Description                                                                            |
| ---           | ---     | ---                                                                                    |
| line1         | string  | The first line of the address.                                                         |
| line2         | string  | The second line of the address.                                                        |
| line3         | string  | The third line of the address.                                                         |
| line4         | string  | The fourth line of the address.                                                        |
| city          | string  | The city of the address.                                                             |
| stateCode     | string  | The state code of the address.                                                       |
| stateName     | string  | The state name of the address.                                                       |
| countryCode   | string  | The country code of the address.                                                     |
| countryName   | string  | The country name of the address.                                                     |
| postalCode    | string  | The postal code of the address.                                                      |

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the events the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

