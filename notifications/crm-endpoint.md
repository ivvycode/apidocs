# CRM Endpoint

This notification will be sent when an opportunity has been modified. <ul><li>Opportunity is updated</li><li>Opportunity is added</li><li>Opportunity is deleted</li><li>Tasks is updated</li><li>Task is created</li><li>Task is deleted</li><li>Activity is updated</li><li>Activity is created</li><li>Activity is deleted</li></ul>

## Opportunity is created.

### Subject
OpportunityAdded

### Body

```json
{
    "data": {... JSON Response from getOpportunityList API }
}
```

## Opportunity is updated.

### Subject
OpportunityUpdated

### Body

```json
{
    "data": {... JSON Response from getOpportunityList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Opportunity is deleted.

### Subject
OpportunityDeleted

### Body

```json
{
    "venueId": 123,
    "opportunityId": 234
}
```

## Task is created

### Subject
CrmEventTaskAdded

### Body

```json
{
    "data": {... JSON Response from getTaskList API }
}
```

## Task is updated

### Subject
CrmEventTaskUpdated

### Body

```json
{
    "data": {... JSON Response from getTaskList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Task is deleted

### Subject
CrmEventTaskDeleted

### Body

```json
{
    "taskId": 123,
}
```

## Activity is created

### Subject
CrmEventActivityAdded

### Body
```json
{
    "data": {... JSON Response from getActivityList API }
}
```

## Activity is updated

### Subject
CrmEventActivityUpdated

### Body

```json
{
    "data": {... JSON Response from getActivityList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```

## Activity is deleted

### Subject
CrmEventActivityDeleted

### Body

```json
{
    "activityId": 123,
}
```