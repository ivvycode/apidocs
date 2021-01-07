# Add or Update Activity Purpose

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=addOrUpdateTask" path="" %}
{% api-method-summary %}
Add or Update Task which belongs contact, company, opportunity and lead
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the task
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=false %}
The unique id of the venue to which the task belongs. Required when assigning the task to opportunity. The api will throw an error for invalid leadId
{% endapi-method-parameter %}

{% api-method-parameter name="leadId" type="integer" required=false %}
The unique id of the opportunity/lead to which the new task belongs
{% endapi-method-parameter %}

{% api-method-parameter name="contactId" type="integer" required=false %}
The unique id of the contact to which the new task belongs
{% endapi-method-parameter %}

{% api-method-parameter name="companyId" type="integer" required=false %}
The unique id of the company to which the new task belongs
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
The name of the task. Required when id is missing.
{% endapi-method-parameter %}

{% api-method-parameter name="endDatetime" type="string" required=false %}
The due date and time of the task. Format is Y-m-d H:i:s and must be in UTC timezone. Required when id is missing.
{% endapi-method-parameter %}

{% api-method-parameter name="priority" type="string" required=false %}
The priority of the task low, medium or high.
{% endapi-method-parameter %}

{% api-method-parameter name="assignedUserId" type="integer" required=false %}
The unique id of the user to which the task will be assigned
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="integer" required=false %}
The status of the task
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
The description of the task
{% endapi-method-parameter %}

{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

Success Response

```text
{
  "success": true,
  "id": 755
}
```

Error Response

```text
{
  "errorCode": 400,
    "message": "The request contains invalid data",
    "specificCode": 24395,
    "additionalMessages": [
        "leadId: *Invalid item selected*"
    ]
}
```

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Task Status

| Id | Name |
| :--- | :--- |
| 0 | Not Started |
| 1 | In Progress |
| 2 | On Hold |
| 3 | Cancelled |
| 4 | Completed |

## Example Request

### Add Activity Purpose

```javascript
{
  "name": "Test Task API",
  "endDatetime": "2021-11-01 17:00:00",
  "status": 1,
  "assignedUserId": 1,
  "leadId": 2665
}
```

### Update Activity Purpose

```javascript
{
  "id": 3269,
  "venueId": 1,
	"name": "Test Task API",
  "endDatetime": "2021-11-01 17:00:00",
  "status": 1,
  "assignedUserId": 1,
  "contactId": 45219,
  "companyId": 854
}
```

## Returns

| Property | Description |
| :--- | :--- |
| success | Whether or not the task was added/updated |
| id | The unique id of the task |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24389 | The lead/opportunity does not exist |
| Specific Code: 24390 | The contact does not exist |
| Specific Code: 24391 | The company does not exist |
| Specific Code: 24392 | The task does not exist |
| Specific Code: 24393 | An error has occurred |
| Specific Code: 24394 | The request contains invalid data. The data was validated but there was some other error. See additional messages |
| Specific Code: 24395 | The request contains invalid data |
| Specific Code: 24396 | The task can only belongs to either contact, company or opportunity/lead |

Task can only belongs to either company, contact or lead. When companyId and contactId both provided the contactId will be added to company as company contact and task will be be associated with company.

