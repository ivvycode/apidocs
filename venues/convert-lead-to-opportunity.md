# Convert Lead To Opportunity

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/venue?action=convertLeadToOpportunity" path="" %}
{% api-method-summary %}
Convert Lead to Opportunity
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="leadId" type="integer" required=true %}
The unique identifier of lead
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=true %}
The unique venue id of opportunity
{% endapi-method-parameter %}

{% api-method-parameter name="stageId" type="integer" required=true %}
The stage of opportunity
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the lead was converted to opportunity or not |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24227 | The request is empty |
| Specific Code: 24228 | The lead does not exist |

