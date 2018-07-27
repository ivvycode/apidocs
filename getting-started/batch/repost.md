# Repost

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/batch?action=repost" path="" %}
{% api-method-summary %}
Repost
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="async" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "reposted":true
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

The repost action takes the asyncId as a parameter and returns the success of the call.

{% hint style="info" %}
Note a success of true does not mean the callback will be hit immediately.
{% endhint %}

## Example Request

`Example: Restart a batch job`

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```

