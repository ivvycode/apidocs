# Add or Update Activity

{% swagger baseUrl="[PlatformAddress]/api/1.0/crm?action=addOrUpdateActivity" method="post" summary="Add or Update Activity which belongs contact, company, opportunity and lead" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter name="id" type="integer" in="path" %}
The unique id of the activity
{% endswagger-parameter %}

{% swagger-parameter name="venueId" type="integer" in="path" %}
The unique id of the venue to which the activity belongs. Required when assigning the activity to opportunity. The api will throw an error for invalid leadId
{% endswagger-parameter %}

{% swagger-parameter name="leadId" type="integer" in="path" %}
The unique id of the opportunity/lead to which the new activity belongs
{% endswagger-parameter %}

{% swagger-parameter name="contactId" type="integer" in="path" %}
The unique id of the contact to which the new activity belongs
{% endswagger-parameter %}

{% swagger-parameter name="companyId" type="integer" in="path" %}
The unique id of the company to which the new activity belongs
{% endswagger-parameter %}

{% swagger-parameter name="name" type="string" in="path" %}
The name of the activity. Required when id is missing.
{% endswagger-parameter %}

{% swagger-parameter name="description" type="string" in="path" %}
The description of the activity. Required when id is missing.
{% endswagger-parameter %}

{% swagger-parameter name="subType" type="integer" in="path" %}
The subtype of activity. Required when id is missing.
{% endswagger-parameter %}

{% swagger-parameter name="purposeId" type="integer" in="path" %}
The unique id of the venue to which the booking belongs
{% endswagger-parameter %}

{% swagger-parameter name="startDatetime" type="timestamp" in="path" %}
The start date and time of the activity. Format is Y-m-d H:i:s and must be in UTC timezone.
{% endswagger-parameter %}

{% swagger-parameter name="endDatetime" type="timestamp" in="path" %}
The end date and time of the activity. Format is Y-m-d H:i:s and must be in UTC timezone.
{% endswagger-parameter %}

{% swagger-parameter name="location" type="string" in="path" %}
The location of the event activity
{% endswagger-parameter %}

{% swagger-parameter name="priority" type="string" in="path" %}
The priority of the activity low, medium or high.
{% endswagger-parameter %}

{% swagger-parameter name="assignedUserId" type="integer" in="path" %}
The unique id of the user to which the activity will be assigned
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

## Activity Sub Type

| Id | Name    |
| -- | ------- |
| 1  | Meeting |
| 2  | Call    |
| 3  | Email   |

## Example Request

### Add Activity

```javascript
{
  "name": "Test Activity API",
  "venueId": 1,
  "subType": 2,
  "purposerId": 1,
  "startDateTime": "2020-02-02 01:00:00 UTC",
  "endDateTime": "2020-02-02 02:00:00 UTC",
  "assignedUserId": 1,
  "leadId": 2665
}
```

### Update Activity

```javascript
{
  "id": 3269,
  "venueId": 1,
  "name": "Test Activity API"
}
```

## Returns

| Property | Description                                   |
| -------- | --------------------------------------------- |
| success  | Whether or not the activity was added/updated |
| id       | The unique id of the activity                 |

## Throws

| Code                 | Description                                                                                                       |
| -------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Specific Code: 24397 | The lead/opportunity does not exist                                                                               |
| Specific Code: 24398 | The contact does not exist                                                                                        |
| Specific Code: 24399 | The company does not exist                                                                                        |
| Specific Code: 24400 | The activity does not exist                                                                                       |
| Specific Code: 24401 | An error has occurred                                                                                             |
| Specific Code: 24402 | The request contains invalid data. The data was validated but there was some other error. See additional messages |
| Specific Code: 24403 | The request contains invalid data                                                                                 |
| Specific Code: 24404 | The activity can only belongs to either contact, company or opportunity/lead                                      |

Activity can only belongs to either company, contact or lead. When companyId and contactId both provided the contactId will be added to company as company contact and activity will be be associated with company.
