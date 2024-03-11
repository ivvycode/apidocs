# CRM Endpoint

This notification will be sent when a opportunity is modified or created.

Here are the `Body` of the example notification messages after parse.

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
