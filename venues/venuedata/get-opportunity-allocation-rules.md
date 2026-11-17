{% swagger baseUrl="[PlatformAddress]/api/1.0/" path="venue?action=getOpportunityAllocationRules" method="post" %}
{% swagger-description %}
Returns the rules that decide who opportunities from the Marketplace and Booking Engine Form are assigned to and who is notified, along with the default used when no rule matches. These are set up under Setup > Online Bookings > Opportunity Allocation Rules.
{% endswagger-description %}

{% swagger-parameter name="venueId" type="integer" in="body" required="true" %}
The id of the venue whose opportunity allocation rules are returned.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```json
{
    "rules": [
        {
            "id": 12,
            "criteria": {
                "opportunityType": 1,
                "eventTypeIds": [3, 5],
                "valueBasis": "value",
                "valueFrom": 1000,
                "valueTo": 5000
            },
            "assignmentType": 2,
            "assignedUsers": [
                {
                    "id": 42,
                    "firstName": "Jane",
                    "lastName": "Smith",
                    "email": "jane.smith@examplevenue.com"
                },
                {
                    "id": 43,
                    "firstName": "Sam",
                    "lastName": "Lee",
                    "email": "sam.lee@examplevenue.com"
                }
            ],
            "notificationEmails": [
                "events@examplevenue.com"
            ],
            "quality": {
                "id": 3,
                "name": "Warm"
            }
        },
        {
            "id": 15,
            "criteria": {
                "opportunityType": 3,
                "eventTypeIds": [],
                "valueBasis": "all",
                "valueFrom": null,
                "valueTo": null
            },
            "assignmentType": 1,
            "assignedUsers": [],
            "notificationEmails": [],
            "quality": null
        }
    ],
    "defaultRule": {
        "assignmentType": 3,
        "assignedUsers": [
            {
                "id": 42,
                "firstName": "Jane",
                "lastName": "Smith",
                "email": "jane.smith@examplevenue.com"
            }
        ],
        "notificationEmails": [
            "reception@examplevenue.com"
        ]
    }
}
```
{% endswagger-response %}

## Example Request
```json
{
    "venueId": 1
}
```
{% endswagger %}

## Rule Order

Rules are returned in the order they are tried. The first rule that matches the opportunity is used, and `defaultRule` applies when none of them match.

## Returns

An object with the following properties

| Property    | Data Type | Description                                                    |
|-------------|-----------|----------------------------------------------------------------|
| rules       | array     | The venue's rules, in the order they are tried. See Rule below  |
| defaultRule | object    | How opportunities are allocated when no rule matches. See Assignment below |

### Rule

| Property           | Data Type | Description |
|--------------------|-----------|-------------|
| id                 | integer   | The unique id of the allocation rule |
| criteria           | object    | The opportunities the rule applies to. See Criteria below |
| assignmentType     | integer   | Who the opportunity is assigned to. See Assignment Types below |
| assignedUsers      | array     | The specific user, or every user in the random pool. Empty when the opportunity is left unassigned. See Assigned User below |
| notificationEmails | array     | The additional email addresses notified of the opportunity |
| quality            | object    | The quality given to the opportunity (`id` and `name`), or null if the rule does not set one |

### Criteria

| Property        | Data Type | Description |
|-----------------|-----------|-------------|
| opportunityType | integer   | Event only (1), accommodation only (2) or event and accommodation (3). The same values as the opportunityType parameter of crm.getHowToAllocateOpportunity |
| eventTypeIds    | array     | The ids of the event types the rule applies to |
| valueBasis      | string    | What the rule compares the opportunity against: `value` (its value), `budgetPercentage` (its value as a percentage of the month's budget) or `all` (every opportunity matches) |
| valueFrom       | integer   | The lowest value or budget percentage the rule matches. Null when valueBasis is `all` |
| valueTo         | integer   | The highest value or budget percentage the rule matches. Null when valueBasis is `all` |

### Assignment

| Property           | Data Type | Description |
|--------------------|-----------|-------------|
| assignmentType     | integer   | Who the opportunity is assigned to. See Assignment Types below |
| assignedUsers      | array     | The specific user, or every user in the random pool. Empty when the opportunity is left unassigned |
| notificationEmails | array     | The additional email addresses notified of the opportunity |

### Assigned User

| Property  | Data Type | Description |
|-----------|-----------|-------------|
| id        | integer   | The unique id of the account user |
| firstName | string    | The first name of the account user |
| lastName  | string    | The last name of the account user |
| email     | string    | The email address of the account user |

### Assignment Types

| Value | Name          | Description |
|-------|---------------|-------------|
| 1     | Unassigned    | The opportunity is left unassigned |
| 2     | Random Pool   | The opportunity is assigned to a random user from assignedUsers |
| 3     | Specific User | The opportunity is assigned to the one user in assignedUsers |
