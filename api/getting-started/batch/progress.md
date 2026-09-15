# Progress

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="batch?action=progress" method="post" summary="Progress" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="async" type="string" in="path" %}
The asyncId for the batch job to check progress for
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "progress":33
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

Fetch the progress of a batch job

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```

## Returns

| Property | Description                                                       |
| -------- | ----------------------------------------------------------------- |
| progress | The progress of the batch job, as a percentage of work completed. |

## Throws

| Code                 | Description          |
| -------------------- | -------------------- |
| Specific Code: 24105 | Could not find batch |

The progress action takes the asyncId as a parameter and returns back the progress of the batch job as a percentage.
