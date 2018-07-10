### addOrUpdateEvent

**Parameters**

| id                     | The event’s unique identifier.                                                                                                                      | Integer               |
|                        | Exclude to add an event.                                                                                                                            | \> 0                  |
|                        | Include to update an existing event.                                                                                                                |                       |
|------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|
| eventType              | Required: always.                                                                                                                                   | Integer               |
|                        | The type of event.                                                                                                                                  | \>= 0                 |
|                        | Value must be 12 (Record Event Details). The value cannot be changed for an existing event.                                                         |                       |
| code                   | The event’s unique code.                                                                                                                            | String                |
|                        | Can be excluded when adding an event (system will assign a unique code). The value cannot be changed for an existing event.                         | Max length: 12        |
| title                  | Required: when adding an event.                                                                                                                     | String                |
|                        | The title of the event.                                                                                                                             | Max length: 140       |
| timezone               | Required: when adding an event. The timezone of the event.                                                                                          | Timezone              |
| startDateTime          | Required: when adding an event.                                                                                                                     | Timestamp             |
|                        | The start date & time of the event.                                                                                                                 |                       |
| endDateTime            | Required: when adding an event.                                                                                                                     | Timestamp             |
|                        | The end date & time of the event.                                                                                                                   |                       |
|                        | The value must be on or after startDateTime.                                                                                                        |                       |
| capacity               | The maximum number of attendees who can register for the event.                                                                                     | Integer               |
|                        | A value of 0 (zero) represents no limit.                                                                                                            | \>= 0                 |
| budget                 | A budget amount assigned to the event.                                                                                                              | Float                 |
| costCenterId           | A cost center assigned to the event. The value is an identifier of a cost center in the account, which must be assignable to events.                | Integer               |
|                        |                                                                                                                                                     | \> 0                  |
| primaryContactUserId   | The primary contact user of the event. The value is an identifier of a user in the account.                                                         | Integer               |
|                        |                                                                                                                                                     | \> 0                  |
| secondaryContactUserId | The secondary contact user of the event. The value is an identifier of a user in the account.                                                       | Integer               |
|                        |                                                                                                                                                     | \> 0                  |
| eventTypeIds           | Zero or more tags assigned to the event.                                                                                                            | Array of Integers     |
|                        | The value is an array of event tag identifiers.                                                                                                     |                       |
| isAccommIncluded       | Whether or not the event requires accommodation.                                                                                                    | Boolean               |
| venueId                | The venue assigned to the event.                                                                                                                    | Integer \> 0          |
|                        | The value is an identifier of an event venue in the account.                                                                                        |                       |

**Returns**

| success | Whether or not the action succeeded (i.e. the event as added or updated). | Boolean              |
|---------|---------------------------------------------------------------------------|----------------------|
| id      | The event’s unique identifier.                                            | Integer              |
|         | The value will be null on failure.                                        | \> 0                 |
| code    | The event’s unique code.                                                  | String               |
|         | The value will be null on failure.                                        | Max length: 12       |

This action call accepts the parameters of an event and will;

1.  Add a new event to the account

2.  Update an existing event in the account when the id parameter is provided.

NOTE: This action call only supports “Record Event Details” type events (i.e.
eventType value of 12).

**Example Request:**

{

"eventType": 12,

"title": "A New Event",

"timezone": "Australia/Sydney",

"startDateTime": "2018-03-05 03:00:00 UTC",

"endDateTime": "2018-03-05 06:00:00 UTC",

"capacity": 10,

"budget": 150,

"costCenterId": 834,

"primaryContactUserId": 7821,

"eventTypeIds": [56,57],

"isAccommIncluded": false

}

**Example Response:**

{

"success": true,

"id": 98481,

"code": "BAS4G248"  
}
