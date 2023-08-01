# Get Venue Rate Plan Rate List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getRatePlanRateList" method="post" summary="Get Venue Rate Plan Rate List" %}
{% swagger-description %}
Get a list of menus.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="barId" type="integer" in="path" %}
The id of the rate plan
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of rate plan rates to get in a single call
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 50,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "barId": 1,
            "startDate": "2019-08-08",
            "endDate": "2022-04-23",
            "minAcceptableRate": 10,
            "daysOfWeek": [
                0,
                1,
                2,
                3,
                4,
                5,
                6
            ]
        },
        {
            "id": 4,
            "barId": 1,
            "startDate": "2023-04-24",
            "endDate": "2023-04-28",
            "minAcceptableRate": 50,
            "daysOfWeek": [
                0,
                6
            ]
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../../getting-started/interpreting-the-response/collections.md) of all the rates the user has access to. This call also accepts the [pagination](../../getting-started/interpreting-the-response/pagination.md) and [filter](../../getting-started/interpreting-the-response/filtering.md) properties.

## Example Request

```javascript
{
  "venueId": 1,
  "barId": 1
}
```

## Rate Plan Rate

| Property              | Type                                                                       | Description                                                                       |
| --------------------- | -------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| id                    | integer                                                                    | The unique id of the rate                                                         |
| barId                 | integer                                                                    | The unique id of the rate plan                                                    |
| startDate             | date                                                                       | The start date of the rate   |
| endDate               | date                                                                       | The end date of the rate |
| minAcceptableRate     | integer                                                                    | The minimum acceptable rate for room rate plan |
| daysOfWeek | array of [Days](get-rate-plan-rate-list#days-of-week)                                 | Days of the week where rate applies  |

## Days of Week

* 0 = Sunday
* 1 = Monday
* 2 = Tuesday
* 3 = Wednesday
* 4 = Thursday
* 5 = Friday
* 6 = Saturday