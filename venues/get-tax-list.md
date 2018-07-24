# Get Tax List

## Description

This API will return all applicable tax list for the venue. venueId is required parameter to get the list of taxes.

## Api Url

`[PlatformAddress]/api/1.0/venue?action=getTaxList`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| venueId | The unique identifier of venue to which taxes belong | Required | integer |

## Returns

`A collection object with the following properties in the results`

| Property | Description |
| --- | --- |
| id | The unique invoice identifier |
| name | The name of Tax |

## Example Request

`Get Venues Tax List`

```javascript
{
  "venueId": 2
}
```

## Example Response

```javascript
{
  "meta": {
    "totalResults": 1,
    "start": 0,
    "perPage": 1,
    "count": 1
  },
  "results": [
    {
      "id": 2,
      "name": "GST"
    }
  ]
}
```

