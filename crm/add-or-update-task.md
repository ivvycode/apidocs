# Add or Update Task

{% swagger baseUrl="[PlatformAddress]/api/1.0/crm?action=addOrUpdateTask" method="post" summary="Add or Update Task which belongs contact, company, opportunity and lead" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the task
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the task belongs. Required when assigning the task to opportunity. The api will throw an error for invalid leadId
{% endswagger-parameter %}

{% swagger-parameter name="leadId" type="integer" in="path" %}
The unique id of the opportunity/lead to which the new task belongs
{% endswagger-parameter %}

{% swagger-parameter name="contactId" type="integer" in="path" %}
The unique id of the contact to which the new task belongs
{% endswagger-parameter %}

{% swagger-parameter name="companyId" type="integer" in="path" %}
The unique id of the company to which the new task belongs
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name of the task. Required when id is missing.
{% endswagger-parameter %}

{% swagger-parameter name="endDatetime" type="timestamp" in="path" %}
The due date and time of the task. Required when id is missing.
{% endswagger-parameter %}

{% swagger-parameter name="priority" type="string" in="path" %}
The priority of the task low, medium or high.
{% endswagger-parameter %}

{% swagger-parameter name="assignedUserId" type="integer" in="path" %}
The unique id of the user to which the task will be assigned
{% endswagger-parameter %}

{% swagger-parameter name="status" type="integer" in="path" %}
The status of the task
{% endswagger-parameter %}

{% swagger-parameter name="description" type="string" in="path" %}
The description of the task
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "success": true,
  "id": 755
}
```
{% endswagger-response %}
{% endswagger %}

## Task Status

| Id | Name        |
| -- | ----------- |
| 0  | Not Started |
| 1  | In Progress |
| 2  | On Hold     |
| 3  | Cancelled   |
| 4  | Completed   |

## Example Request

### Add Task

```javascript
{
  "name": "Test Task API",
  "endDatetime": "2021-11-01 17:00:00",
  "status": 1,
  "assignedUserId": 1,
  "leadId": 2665
}
```

### Update Task

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

| Property | Description                               |
| -------- | ----------------------------------------- |
| success  | Whether or not the task was added/updated |
| id       | The unique id of the task                 |

## Throws

| Code                 | Description                                                                                                       |
| -------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Specific Code: 24389 | The lead/opportunity does not exist                                                                               |
| Specific Code: 24390 | The contact does not exist                                                                                        |
| Specific Code: 24391 | The company does not exist                                                                                        |
| Specific Code: 24392 | The task does not exist                                                                                           |
| Specific Code: 24393 | An error has occurred                                                                                             |
| Specific Code: 24394 | The request contains invalid data. The data was validated but there was some other error. See additional messages |
| Specific Code: 24395 | The request contains invalid data                                                                                 |
| Specific Code: 24396 | The task can only belongs to either contact, company or opportunity/lead                                          |

Task can only belongs to either company, contact or lead. When companyId and contactId both provided the contactId will be added to company as company contact and task will be be associated with company.
