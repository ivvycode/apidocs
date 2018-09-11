---
description: 'NOTE: This action has not been published.'
---

# Get Venue Room Option List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=getVenueRoomOptionList" path="" %}
{% api-method-summary %}
Get Venue Room Option List 
{% endapi-method-summary %}

{% api-method-description %}
Get a list of room options for a venue.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="venueId" type="integer" required=true %}
The unique id of the venue to which the room options belong
{% endapi-method-parameter %}

{% api-method-parameter name="start" type="integer" required=false %}
The starting result of the page. Note this is zero based \(i.e. sending start=0 will start from the first result.\)
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=true %}
The number of booking accomodation groups to fetch
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 100,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "venueId": 1,
            "name": "Test Room Option 1",
            "description": "Test Room Option 1",
            "price": 100,
            "priceExcludedTaxIds": [1],
            "cost": 100,
            "costExcludedTaxIds": [1],
            "costcenterId": null,
            "createdDate": "2018-08-08 12:37:14 UTC",
            "modifiedDate": "2018-08-08 12:37:14 UTC"
        },
        {
            "id": 2,
            "venueId": 1,
            "name": "Test Room Option 2",
            "description": "Test Room Option 2",
            "price": 100,
            "priceExcludedTaxIds": [1],
            "cost": 100,
            "costExcludedTaxIds": [1],
            "costcenterId": null,
            "createdDate": "2018-08-08 18:21:59 UTC",
            "modifiedDate": "2018-08-08 18:21:59 UTC"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of room options the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

## Venue Room Option

| Property | Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the room option |
| venueId | integer | The unique id of the venue to which the room option belongs |
| name | string | The name of the room option (e.g. "Breakfast") |
| description | string | The description of the room option. This can be html formatted text |
| price | number | The sale price of the room option. The amount either includes or excludes tax depending on how the venue is configured |
| priceExcludedTaxIds | array | The array of integers representing the unique ids of the taxes excluded from price |
| cost | number | The cost of the room option. The amount either includes or excludes tax depending on how the venue is configured |
| costExcludedTaxIds | array | The array of integers representing the unique ids of the taxes exlucded from cost |
| costcenterId | integer | The unique id of the cost center assigned to the room option |
| createdDate | datetime | The date & time the room option was created |
| modifiedDate | datetime | The date & time the room option was last modified |
