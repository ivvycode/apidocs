# Get Industry List

{% swagger baseUrl="[PlatformAddress]/api/1.0/account?action=getIndustryList" method="post" summary="Get Industry List" %}
{% swagger-description %}
Fetches the list of industries in the account.
{% endswagger-description %}

{% swagger-parameter name="perPage" type="integer" in="path" %}
The number of industries to get in a single api call. max is 100.
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="path" %}
The starting result of the page. Note this is zero based (i.e. sending start = 0 will start from the first result.)
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Returns

| Property      | Description                                                                                |
| ------------- | ------------------------------------------------------------------------------------------ |
| id            | The unique identifier for the industry                                                     |
| name          | The name of the industry                                                                   |
| createdDate   | The date & time the industry was created                                                   |
| modifiedDate  | 'The date & time the industry was last modified                                            |

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of all the users. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.
