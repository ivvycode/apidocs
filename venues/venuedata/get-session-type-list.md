# Get Session Type List

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=getSessionTypeList" method="post" summary="Get Session Type List" %}
{% swagger-description %}
Return the venue session type list for the account.
{% endswagger-description %}

{% swagger-response status="200" description="" %}
```
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
      "name": "Session Type"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

`Get Session Type List`

```javascript
{}
```

## Returns

`A collection object with the following properties in the results`

| Property      | Type    | Description |
| ------------- | ------- | ---------------------------------- |
| id            | integer | The unique session type identifier |
| name          | integer | The name of Session TYpe |