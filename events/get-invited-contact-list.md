# Get Invited Contact List

## Get Invited Contact List

{% swagger baseUrl="[PlatformAddress]/api/1.0/event?action=getInvitedContactList" method="post" summary="Get Invited Contact List" %}
{% swagger-description %}
Get a list of invited contact for event.
{% endswagger-description %}

{% swagger-parameter name="eventId" type="integer" in="body" %}
The unique id of the event to which the invitation belong
{% endswagger-parameter %}

{% swagger-parameter name="start" type="integer" in="body" %}
The starting result of the page. Note this is zero based (i.e. sending start=0 will start from the first result.)
{% endswagger-parameter %}

{% swagger-parameter name="perPage" type="integer" in="body" %}
The number of invited contacts to fetch
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "meta": {
        "totalResults": 345,
        "start": 0,
        "perPage": 2,
        "count": 2
    },
    "results": [
        {
            "eventId": 1,
            "contactId": 1,
            "firstName": "Test",
            "lastName": "Last",
            "email": "first@test.com",
            "phone": "1346789798",
            "response": "Y",
            "registrationId": 1,
            "modifiedDate": "2018-09-19 09:00:34 UTC"
        },
        {
            "eventId": 1,
            "contactId": 2,
            "firstName": "Test",
            "lastName": "Two",
            "email": "test@two.com",
            "phone": "+61 123456789",
            "response": "U",
            "registrationId": null,
            "modifiedDate": "2018-09-19 08:57:11 UTC"
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

The result from this call will be a [collection](../getting-started/interpreting-the-response/collections.md) of invited contact records the user has access to. This call also accepts the [pagination](../getting-started/interpreting-the-response/pagination.md) and [filter](../getting-started/interpreting-the-response/filtering.md) properties.

### Returns

| Property       | Description                                                                   | Type     |
| -------------- | ----------------------------------------------------------------------------- | -------- |
| eventId        | The unique id of the event for invited contact                                | integer  |
| contactId      | The unique contact id of the invited contact                                  | integer  |
| firstName      | The first name of the invited contact                                         | integer  |
| lastName       | The last name of the invited contact                                          | integer  |
| email          | The email of the invited contact                                              | string   |
| phone          | The phone number of the invited contact                                       | string   |
| response       | The [response](get-invited-contact-list.md#response) from the invited contact | string   |
| registrationId | The registration id of the invited contact                                    | integer  |
| modifiedDate   | The date & time the invited contact was last modified                         | datetime |

### Response

| Status | Description |
| ------ | ----------- |
| U      | Undecided   |
| Y      | Yes         |
| N      | No          |
