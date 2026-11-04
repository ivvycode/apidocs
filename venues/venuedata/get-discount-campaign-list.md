{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getDiscountCampaignList" method="post" %}
{% swagger-description %}
Provides the list of venue discount campaigns set up on the account
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" required="false" %}
Narrows the list to campaigns covering the given venue, whether they name the venue directly or one of the venue groups it belongs to. Accepts a single id or an array of ids. Omit it to return every campaign on the account.
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
            "id": 59,
            "name": "Winter Special",
            "code": "WINTER",
            "description": "20% off room hire",
            "discountType": 1,
            "appliedToType": 1,
            "forBookingItem": 2,
            "venueIds": [
                1,
                2
            ],
            "venueGroupIds": [],
            "startDateTime": "2026-06-01 00:00:00",
            "endDateTime": "2026-08-31 23:59:59",
            "dateEventStart": "2026-07-01",
            "dateEventEnd": "2026-09-30",
            "minBookingValue": 5000,
            "minBookingValueCostcenterIds": [
                11,
                12
            ],
            "minBookingAttendees": 20,
            "minRoomNights": 2,
            "maxUse": 50,
            "maxPax": 200,
            "costcentersDiscounts": [
                {
                    "id": 11,
                    "value": 20
                }
            ],
            "createdDate": "2026-01-05 09:30:00",
            "modifiedDate": "2026-02-11 14:15:00"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`getDiscountCampaignList`

```javascript
{
    "venueId": 1,
    "perPage": 2
}
```

Campaigns belong to the account rather than to a single venue, so `venueId` is optional. A request with no parameters returns every enabled campaign on the account.

To narrow to several venues at once, pass an array:

```javascript
{
    "venueId": [1, 2, 3]
}
```

A campaign is returned when it covers **any** of the venues given, and it is returned only once no matter how many of them it covers.

## Returns

`A collection object with the following properties in the results`

| Property                     | Data Type   | Description                                                                                     |
|------------------------------|-------------|-------------------------------------------------------------------------------------------------|
| id                           | integer     | The unique identifier of the discount campaign                                                  |
| name                         | string      | The name of the discount campaign                                                               |
| code                         | string      | The code a booker enters to redeem the campaign. Always returned in upper case                  |
| description                  | string      | A description of the discount campaign                                                          |
| discountType                 | enum [DiscountType](get-discount-campaign-list.md#discount-type) | Whether the cost center amounts are a percentage or a flat rate |
| appliedToType                | enum [AppliedToType](get-discount-campaign-list.md#applied-to-type) | Whether the campaign is applied to venues or venue groups. Null when the campaign has never been scoped |
| forBookingItem               | enum [ForBookingItem](get-discount-campaign-list.md#for-booking-item) | Whether the campaign applies to all booking items or only packages |
| venueIds                     | array       | The venues the campaign applies to. Only populated when appliedToType is "Venues", otherwise empty |
| venueGroupIds                | array       | The venue groups the campaign applies to. Only populated when appliedToType is "Venue Groups", otherwise empty |
| startDateTime                | datetime    | The UTC date and time from which the campaign can be redeemed                                   |
| endDateTime                  | datetime    | The UTC date and time after which the campaign can no longer be redeemed                        |
| dateEventStart               | date        | The earliest event start date a booking may have to qualify                                     |
| dateEventEnd                 | date        | The latest event end date a booking may have to qualify                                         |
| minBookingValue              | float       | The minimum booking value required to qualify                                                   |
| minBookingValueCostcenterIds | array       | The account cost centers counted towards minBookingValue                                        |
| minBookingAttendees          | integer     | The minimum number of attendees required to qualify                                             |
| minRoomNights                | integer     | The minimum room nights required to qualify                                                     |
| maxUse                       | integer     | The maximum number of times the code can be redeemed. 0 means unlimited                         |
| maxPax                       | integer     | The maximum pax the campaign applies to                                                         |
| costcentersDiscounts         | array of [Cost Center Discounts](get-discount-campaign-list.md#cost-center-discount) | The discount to take off each cost center, read per discountType |
| createdDate                  | datetime    | The date and time the campaign was created                                                      |
| modifiedDate                 | datetime    | The date and time the campaign was last modified                                                |

`startDateTime` and `endDateTime` are returned in UTC.

## Cost Center Discount

| Property       | Data Type | Description                                                                              |
|----------------|-----------|------------------------------------------------------------------------------------------|
| id             | integer   | The cost center identifier                                                               |
| value          | float     | A percentage off when discountType is "Percentage", or a flat amount when it is "Flat Rate" |

## Discount Type

| Identifier | Description    |
|------------|----------------|
| 1          | Percentage (%) |
| 2          | Flat Rate      |

## Applied To Type

| Identifier | Description  |
|------------|--------------|
| 1          | Venues       |
| 2          | Venue Groups |

## For Booking Item

| Identifier | Description   |
|------------|---------------|
| 1          | All           |
| 2          | Only Packages |

Only enabled campaigns are returned; disabled ones are excluded.

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of the discount campaigns on the account. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Filter Columns

The filter property applies only to the following columns:

| Column |
|--------|
| id |
| name |
| code |
| createdDate |
| modifiedDate |

`venueId` is a parameter of its own rather than a filter column, because a campaign reaches a venue through `venueIds` or `venueGroupIds` rather than through a column of its own.
