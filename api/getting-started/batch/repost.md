# Repost

{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="batch?action=repost" method="post" summary="Repost" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="async" type="string" in="path" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "reposted":true
}
```
{% endswagger-response %}
{% endswagger %}

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
