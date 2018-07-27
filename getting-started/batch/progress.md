# Progress

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/batch?action=progress" path="" %}
{% api-method-summary %}
Progress
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="async" type="string" required=true %}
The asyncId for the batch job to check progress for
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ 
  "progress":33
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

Fetch the progress of a batch job

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```

## Returns

| Property | Description |
| --- | --- |
| progress | The progress of the batch job, as a percentage of work completed. |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24105 | Could not find batch |

The progress action takes the asyncId as a parameter and returns back the progress of the batch job as a percentage.

