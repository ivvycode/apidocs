# Add or Update Activity

{% api-method method="post" host="\[PlatformAddress\]/api/1.0/crm?action=addOrUpdateActivity" path="" %}
{% api-method-summary %}
Add or Update Activity which belongs contact, company, opportunity and lead
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=false %}
The unique id of the activity
{% endapi-method-parameter %}

{% api-method-parameter name="venueId" type="integer" required=false %}
The unique id of the venue to which the activity belongs. Required when assigning the activity to opportunity. The api will throw an error for invalid leadId
{% endapi-method-parameter %}

{% api-method-parameter name="leadId" type="integer" required=false %}
The unique id of the opportunity/lead to which the new activity belongs
{% endapi-method-parameter %}

{% api-method-parameter name="contactId" type="integer" required=false %}
The unique id of the contact to which the new activity belongs
{% endapi-method-parameter %}

{% api-method-parameter name="companyId" type="integer" required=false %}
The unique id of the company to which the new activity belongs
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
The name of the activity. Required when id is missing.
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
The description of the activity. Required when id is missing.
{% endapi-method-parameter %}

{% api-method-parameter name="subType" type="integer" required=false %}
The subtype of activity. Required when id is missing.
{% endapi-method-parameter %}

{% api-method-parameter name="purposeId" type="integer" required=false %}
The unique id of the venue to which the booking belongs
{% endapi-method-parameter %}

{% api-method-parameter name="startDatetime" type="timestamp" required=false %}
The start date and time of the activity. Format is Y-m-d H:i:s and must be in UTC timezone.
{% endapi-method-parameter %}

{% api-method-parameter name="endDatetime" type="timestamp" required=false %}
The end date and time of the activity. Format is Y-m-d H:i:s and must be in UTC timezone.
{% endapi-method-parameter %}

{% api-method-parameter name="location" type="string" required=false %}
The location of the event activity
{% endapi-method-parameter %}

{% api-method-parameter name="priority" type="string" required=false %}
The priority of the activity low, medium or high.
{% endapi-method-parameter %}

{% api-method-parameter name="assignedUserId" type="integer" required=false %}
The unique id of the user to which the activity will be assigned
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
    "specificCode": 24403,
    "additionalMessages": [
        "leadId: *Invalid item selected*"
    ]
}
```

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Activity Sub Type

| Id | Name |
| :--- | :--- |
| 1 | Meeting |
| 2 | Call |
| 3 | Email |

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

| Property | Description |
| :--- | :--- |
| success | Whether or not the activity was added/updated |
| id | The unique id of the activity |

## Throws

| Code | Description |
| :--- | :--- |
| Specific Code: 24397 | The lead/opportunity does not exist |
| Specific Code: 24398 | The contact does not exist |
| Specific Code: 24399 | The company does not exist |
| Specific Code: 24400 | The activity does not exist |
| Specific Code: 24401 | An error has occurred |
| Specific Code: 24402 | The request contains invalid data. The data was validated but there was some other error. See additional messages |
| Specific Code: 24403 | The request contains invalid data |
| Specific Code: 24404 | The activity can only belongs to either contact, company or opportunity/lead |

Activity can only belongs to either company, contact or lead. When companyId and contactId both provided the contactId will be added to company as company contact and activity will be be associated with company.

