# Result

{% swagger baseUrl="[PlatformAddress]/api/1.0/batch?action=results" method="post" summary="Results" %}
{% swagger-description %}
The results action takes the asyncId as a parameter and fetch the results of a batch request after it has been executed.
{% endswagger-description %}

{% swagger-parameter name="async" type="string" in="path" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "asyncId": "e35e06ee592d17a42dc9e6252a058617",
  "results": [
    {
      "namespace": "event",
      "action": "inviteContacts",
      "request": {
        "event": 1,
        "contacts": [1, 2, 3]
      },
      "response": {
        // Response data for the first job
      }
    },
    {
      "namespace": "event",
      "action": "inviteContacts",
      "request": {
        "event": 2,
        "contacts": [1, 2, 4]
      },
      "response": {
        // Response data for the second job
      }
    },
    // Additional results for other jobs in the batch
  ]
}

```
{% endswagger-response %}

{% hint style="info" %}
Please note that the data will not be available after 2 days.
{% endhint %}

{% endswagger %}

## Example Request

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```

## Returns

The response will be a JSON object with the following keys:

* asyncId: The async identifier provided when the batch was created.
* results: An array of objects for each result of the batch, with the following keys:
  * namespace: The namespace of the call for the response.
  * action: The action of the call for the response.
  * request: The original request parameters used.
  * response: The response of the API call.

## Throws

| Code                 | Description                   |
| -------------------- | ----------------------------- |
| Specific Code: 24114 | Batch job not completed          |
| Specific Code: 24115 | Could not find batch     |


This structure facilitates retrieving the results of each individual job within the batch request, along with the corresponding request parameters and response data, or it indicates that the batch job is not yet completed. Please note that the data will not be available after 2 days.
