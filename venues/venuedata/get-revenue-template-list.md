# Get Revenue Template List

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/" path="venue?action=getRevenueTemplateList" %}
{% api-method-summary %}
Get Venue Revenue Template List
{% endapi-method-summary %}

{% api-method-description %}
Return the event type list for the account.
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
        "totalResults": 2,
        "start": 0,
        "perPage": 100,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "name": "Banquet",
            "isDefault": true,
            "costcenters": [
                {
                    "costcenterId": 1,
                    "newCostcenterId": 1102
                },
                {
                    "costcenterId": 2,
                    "newCostcenterId": 1109
                },
                {
                    "costcenterId": 4,
                    "newCostcenterId": 4
                }
            ],
            "createdDate": "2021-03-03 11:22:20 UTC",
            "modifiedDate": "2021-03-15 14:19:47 UTC"
        },
        {
            "id": 2,
            "name": "Catering",
            "isDefault": false,
            "costcenters": [
                {
                    "costcenterId": 1,
                    "newCostcenterId": 1101
                },
                {
                    "costcenterId": 2,
                    "newCostcenterId": 1110
                }
            ],
            "createdDate": "2021-03-03 11:22:35 UTC",
            "modifiedDate": "2021-03-15 04:41:59 UTC"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

`Get Venues Revenue Template List`

```javascript
{
"venueId" : 1
"perPage": 100
"start": 0
}
```
## Returns

`A collection object with the following properties in the results`

| Property | Description |
| :--- | :--- |
| id | The unique id of the revenue template |
| name | The name of the revenue template |
| isDefault | Whether or not the revenue template is default on venue. |
| costcenters | The cost center mapping of the revenue template. See [Mapping](get-revenue-template-list.md#mapping) |
| createdDate | The date & time the revenue template was created |
| modifiedDate | The date & time the revenue template was last modified |

## Mapping

| Property | Description |
| :--- | :--- |
| costcenterId | The current cost center |
| newCostcenterId | The new cost center against current cost center |
