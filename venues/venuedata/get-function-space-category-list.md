# Get Function Space Category List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="venue?action=getFunctionSpaceCategoryList" %}
{% api-method-summary %}
Get Venue Function Space Category List
{% endapi-method-summary %}

{% api-method-description %}
Return the venue function space category list for the venue.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The id of the venue
{% endapi-method-parameter %}

{% api-method-parameter name="perPage" type="integer" required=false %}
The number of menu to get in a single call
{% endapi-method-parameter %}

{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "meta": {
        "totalResults": 5,
        "start": 0,
        "perPage": 10,
        "count": 5
    },
    "results": [
        {
            "id": 2,
            "name": "B Category"
        },
        {
            "id": 1,
            "name": "A Category"
        },
        {
            "id": 3,
            "name": "C"
        },
        {
            "id": 4,
            "name": "abc"
        },
        {
            "id": 5,
            "name": "D Category"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get Venues Function Space Category List`

```javascript
{
    "venueId": 1,
    "perPage":10
}
```

## Returns

`A collection object with the following properties in the results`

| Property | Data Type | Description |
| :--- | :--- | :--- |
| id | integer | The unique id of the space category. |
| name | string | The name of the space category. |

### Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24150 | Account does not exist |
| Specific Code: 24102 | Venue does not exist |
| Specific Code: 24408 | Feature not allowed |