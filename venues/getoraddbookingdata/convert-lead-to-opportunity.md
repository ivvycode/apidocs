# Convert Lead To Opportunity

{% swagger baseUrl="[PlatformAddress]/api/1.0/venue?action=convertLeadToOpportunity" method="post" summary="Convert Lead to Opportunity" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="leadId" type="integer" in="path" %}
The unique identifier of lead
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique venue id of opportunity
{% endswagger-parameter %}

{% swagger-parameter name="stageId" type="integer" in="path" %}
The stage of opportunity
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

## Returns

| Property | Description                                                 |
| -------- | ----------------------------------------------------------- |
| success  | Whether or not the lead was converted to opportunity or not |

## Throws

| Code                 | Description             |
| -------------------- | ----------------------- |
| Specific Code: 24227 | The request is empty    |
| Specific Code: 24228 | The lead does not exist |
