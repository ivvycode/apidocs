# Restart

{% swagger baseUrl="[PlatformAddress]/api/1.0/batch?action=restart" method="post" summary="Restart" %}
{% swagger-description %}
The restart action takes the asyncId as a parameter and returns the success of the call. Note a success of true does not mean the job will restart immediately
{% endswagger-description %}

{% swagger-parameter name="" type="string" in="path" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "restarted":true
}
```
{% endswagger-response %}
{% endswagger %}

## Example Request

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```
