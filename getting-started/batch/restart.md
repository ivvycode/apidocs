# Restart

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/batch?action=restart" path="" %}
{% api-method-summary %}
Restart
{% endapi-method-summary %}

{% api-method-description %}
The restart action takes the asyncId as a parameter and returns the success of the call. Note a success of true does not mean the job will restart immediately
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "restarted":true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```

