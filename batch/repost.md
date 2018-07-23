# Repost

## Description

The repost action takes the asyncId as a parameter and returns the success of the call. 

{% hint style="info" %}
Note a success of true does not mean the callback will be hit immediately.
{% endhint %}

## API URL

`[PlatformAddress]/api/1.0/batch?action=repost`

## Example Request

`Example: Restart a batch job`

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```

## Example Response

```javascript
{
  "reposted":true
}
```

