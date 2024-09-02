# Get Resource List

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getResourceList" method="post" summary="Get Venue Resources List" %}
{% swagger-description %}
Return the venue resource list for the venue.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The id of the venue
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 2,
        "start": 0,
        "perPage": 100,
        "count": 2
    },
    "results": [
        {
            "id": 3,
            "venueId": 1,
            "name": "Resource 1",
            "code": "",
            "categoryId": 1,
            "shortDescription": "",
            "longDescription": null,
            "quantity": 12,
            "canBookByHour": true,
            "hourlyCost": 0,
            "dailyCost": 10,
            "isRestrictedToSpaces": true,
            "hasSubResources": false,
            "costcenterId": 3,
            "isViewable": true,
            "createdDate": "2017-12-20 11:09:38 UTC",
            "modifiedDate": "2020-11-10 06:51:47 UTC"
        },
        {
            "id": 24,
            "venueId": 1,
            "name": "Resource 2",
            "code": "",
            "categoryId": 1,
            "shortDescription": "",
            "longDescription": null,
            "quantity": null,
            "canBookByHour": true,
            "hourlyCost": 0,
            "dailyCost": 0,
            "isRestrictedToSpaces": true,
            "hasSubResources": true,
            "costcenterId": 3,
            "isViewable": true,
            "createdDate": "2020-11-10 06:59:29 UTC",
            "modifiedDate": "2020-11-10 06:59:29 UTC"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Venues Resource List`

```javascript
{
  "venueId": 2
}
```

## Returns

`A collection object with the following properties in the results`

| Property                 | Description                                            |
| ------------------------ | ------------------------------------------------------ |
| id                       | The unique invoice identifier                          |
| venueId                  | The id of the venue to which the resource belongs      |
| name                     | The name of the resource                               |
| code                     | The code of the resource                               |
| categoryId               | The category of the resource                           |
| shortDescription         | The short description of the resource                  |
| longDescription          | The long description of the resource                   |
| quantity                 | The quantity of the resource                           |
| canBookByHour            | Whether or not the resource can be booked by hour      |
| hourlyCost               | Hourly cost of the resource                            |
| hourlyCostExcludedTaxIds | Details of taxes                                       |
| dailyCost                | Daily cost of the resource                             |
| dailyCostExcludedTaxIds  | Details of taxes                                       |
| isRestrictedToSpaces     | Whether or not this resource is restricted to spaces   |
| hasSubResources          | Whether or not this resource has sub resources         |
| subResourceIds           | ids of sub resources                                   |
| costcenterId             | The costcenter id of the resource                      |
| isViewable               | Whether or not the resource is viewable on marketplace |
| createdDate              | The date & time the resource was created               |
| modifiedDate             | The date & time the resource was last modified         |
