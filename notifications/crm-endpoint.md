# CRM Endpoint

This notification will be sent when an opportunity has been modified. <ul><li>Opportunity is updated</li><li>Opportunity is added</li><li>Opportunity is deleted</li><li>Tasks is updated</li><li>Task is created</li><li>Task is deleted</li><li>Activity is updated</li><li>Activity is created</li><li>Activity is deleted</li></ul>

## Opportunity is created.

```json
{
    "data": {... JSON Response from getOpportunityList API }
}
```
Subject: **OpportunityAdded**


## Opportunity is updated.
```json
{
    "data": {... JSON Response from getOpportunityList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **OpportunityUpdated**


## Opportunity is deleted.

```json
{
    "venueId": 123,
    "opportunityId": 234
}
```
Subject: **OpportunityDeleted**


## Task is created
```json
{
    "data": {... JSON Response from getTaskList API }
}
```
Subject: **CrmEventTaskAdded**


## Task is updated

```json
{
    "data": {... JSON Response from getTaskList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **CrmEventTaskUpdated**

## Task is deleted

```json
{
    "taskId": 123,
}
```
Subject: **CrmEventTaskDeleted**

## Activity is created
```json
{
    "data": {... JSON Response from getActivityList API }
}
```
Subject: **CrmEventActivityAdded**

## Activity is updated

```json
{
    "data": {... JSON Response from getActivityList API },
    "previousData": {... Previous Data in JSON which has been just updated }
}
```
Subject: **CrmEventActivityUpdated**

## Activity is deleted

```json
{
    "activityId": 123,
}
```
Subject: **CrmEventActivityDeleted**
