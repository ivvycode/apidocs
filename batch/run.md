# Run

## API URL

`[PlatformAddress]/api/1.0/batch?action=run`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| jobs | Array of api jobs to be run on the api. Each job needs to have the [keys](run.md#keys). | Required | string |
| callbackUrl | The URL to hit with a POST request after the batch has been run, with a JSON object of the responses | Required | string |

## Keys

| namespace |
| --- |
| action |
| params |

## Returns

| Property | Description |
| --- | --- |
| asyncId | Identifier for the batch request |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24092 | Incorrect Job Format |
| Specific Code: 24093 | Empty job parameter found |
| Specific Code: 24091 | The information was not saved |

The run action takes an array of api calls and returns an identifier that can be used to identify the batch. Keep this identifier as it can be used to identify the response of the batch request, as well as being used to fetch the progress and results of the request.

To run a batch job, an JSON object must be provided with the following keys:

* jobs: An array of jobs, each element being an object with the following keys
  * namespace: The namespace of the api call
  * action: The api call to make
  * params: Any parameters required for the api call
* callbackUrl: A URL that will be called after the batch has completed.
  * The request will be a POST request
  * The response will be a JSON object with the following keys
    * asyncId: The async identifier provided when the batch was created
    * results: An array of objects for each result of the batch, with the following keys
      * namespace: The namespace of the call for the response
      * action: The action of of the call for the response
      * request: The original request parameters used
      * response: The response of the api call

## Example Request

```javascript
{ 
  "jobs":[{"namespace":"event",”action:"inviteContacts","params":{"event":1,"contacts":[1,2,3]}},     {"namespace":"event",”action:"inviteContacts","params":{"event":2,"contacts":[1,2,4]}},],
  "callbackUrl":"http://example.callback.url.com"
}
```

## Example Response

```javascript
{
    "asyncId":"e35e06ee592d17a42dc9e6252a058617"
}
```

