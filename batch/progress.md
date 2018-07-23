# Progress

## API URL

`[PlatformAddress]/api/1.0/batch?action=progress`

## Parameters

| Property | Description | Required | Type |
| --- | --- | --- | --- |
| async | The asyncId for the batch job to check progress for | Required | string |

## Returns

| Property | Description |
| --- | --- |
| progress | The progress of the batch job, as a percentage of work completed. |

## Throws

| Code | Description |
| --- | --- |
| Specific Code: 24105 | Could not find batch |

The progress action takes the asyncId as a parameter and returns back the progress of the batch job as a percentage.

## Example Request

Fetch the progress of a batch job

```javascript
{
  "async":"a7ec88af7d710bf51b188004bb532d77"
}
```

## Example Response

```javascript
{ 
  "progress":33
}
```

