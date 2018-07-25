# Restart

## Description

The restart action takes the asyncId as a parameter and returns the success of the call. Note a success of true does not mean the job will restart immediately.

## API URL

`[PlatformAddress]/api/1.0/batch?action=restart`

## Example Request

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```

## Example Response

```javascript
{
  "restarted":true
}
```

