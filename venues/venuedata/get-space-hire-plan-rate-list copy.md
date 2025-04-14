# Get Space Hire Plan Rate List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getSpaceHirePlanRateList" method="post" summary="Get Space Hire Plan Rate List" %}
{% swagger-description %}
Return the space hire plan rates list for the venue.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-parameter name="tariffId" type="integer" in="path" %}
The id of the space hire plan
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
            "id": 9,
            "venueId": 1,
            "tariffId": 8,
            "colour": "#e4afaf",
            "startDate": "2021-01-09",
            "endDate": "2021-01-16",
            "daysOfWeek": [
                0
            ],
            "createdDate": "2021-01-08 12:01:22 UTC",
            "modifiedDate": "2022-10-24 07:57:22 UTC"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Space Hire Plan Rate List`

```javascript
{
  "venueId": 1,
  "tariffId": 8,
  "perPage": 100
}
```
You can use `startDateFilter` and `endDateFilter` in [filter](../../getting-started/interpreting-the-response/filtering.md) to object to filter space hire plan rates within specific timeframe

## Returns

`A collection object with the following properties in the results`

| Property                    | Data Type | Description                                                                                                                                                                                                                              |
| --------------------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id | int | The unique identifier of the tariff rate |
| venueId | int | The venue identifier of the tariff rate |
| tariffId | int | The unique identifier of the tariff |
| colour |  string |  The colour to identify the tariff rate |
| startDate | sqldate |The start date of tariff rate |
| endDate | sqldate | The end date of tariff rate |
| daysOfWeek |  array | The days of the week to which the tariff rate applies |
| createdDate | timestamp | The date & time the tariff rate was created |
| modifiedDate | timestamp | The date & time the tariff rate was last modified |

## daysOfWeek:

following values:

* 0 = Sunday
* 1 = Monday
* 2 = Tuesday
* 3 = Wednesday
* 4 = Thursday
* 5 = Friday
* 6 = Saturday