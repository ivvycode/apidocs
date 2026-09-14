# Get Event Type List

<mark style="color:green;">`POST`</mark> `[PlatformAddress]/api/1.0/venue?action=getEventTypeList`

Return the event type list for the account.

{% tabs %}
{% tab title="200 " %}
```
{
    "meta": {
        "totalResults": 11,
        "start": 0,
        "perPage": 2,
        "count": 2
    },
    "results": [
        {
            "id": 1,
            "name": "Christmas",
            "description": null,
            "marketplaceEventType": 11,
            "contactType": 0,
            "isViewable": true,
            "createdDate": "2017-12-18 09:48:05 UTC",
            "modifiedDate": "2017-12-18 09:48:05 UTC"
            "subTypes": [
                {
                    "id": 1,
                    "name": "Christmas Eve"
                }
            ]
        },
        {
            "id": 2,
            "name": "Cocktail",
            "description": null,
            "marketplaceEventType": 11,
            "contactType": 0,
            "isViewable": true,
            "createdDate": "2017-12-18 09:48:05 UTC",
            "modifiedDate": "2017-12-18 09:48:05 UTC"
            "subTypes": []
        }
    ]
}
```
{% endtab %}
{% endtabs %}

### Example Request

`Get Venues Event Type List`

```javascript
{
"perPage": 10
"start": 0
}
```

### Returns

`A collection object with the following properties in the results`

| Property             | Description                                                                                                                                                                                                          |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                   | The unique event type identifier                                                                                                                                                                                     |
| name                 | The name of the event type                                                                                                                                                                                           |
| description          | The description of the event type                                                                                                                                                                                    |
| marketplaceEventType | The Venue Marketplace event type to associate with the event type. See [Marketplace Event Types](https://github.com/ivvycode/apidocs/blob/master/venues/venuedata/get-event-type-list.md.md#marketplace-event-types) |
| contactType          | The type of contact that can be assigned to a opportunity/booking of the event type. 0 = Company & Contact, 1 = Company, 2 = Contact                                                                                 |
| isViewable           | Whether or not the event type is viewable on marketplace                                                                                                                                                             |
| createdDate          | The date & time the event type was created                                                                                                                                                                           |
| modifiedDate         | The date & time the event type was last modified                                                                                                                                                                     |
| subTypes             | Array of [Event Sub Type](get-event-type-list.md#event-sub-type)                                                                                                                                                     |

### Marketplace Event Types

| #  | Description        |
| -- | ------------------ |
| 2  | Christmas          |
| 3  | Cocktail           |
| 4  | Conference         |
| 5  | Corporate Function |
| 13 | Breakfast          |
| 14 | Lunch              |
| 6  | Dinner             |
| 11 | Event              |
| 7  | Exhibition         |
| 8  | Meeting            |
| 9  | Party              |
| 10 | Wedding            |
| 1  | Other              |

### Event Sub Type

| Property | Description                          |
| -------- | ------------------------------------ |
| id       | The unique event sub type identifier |
| name     | The name of the event sub type       |
