# # WebhookSetJsonPostRequestEventsByUserInner

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**userId** | **int** | Unique user identifier. | | 11344 |  true 
**projectId** | **string** | Project identifier, present only if webhook was registered for the project using project API key. | | null | 
**projectName** | **string** | Project name, present only if webhook was registered for the project using project API key. | | null | 
**events** | [**\UniOne\Model\WebhookSetJsonPostRequestEventsByUserInnerEventsInner[]**](WebhookSetJsonPostRequestEventsByUserInnerEventsInner.md) | Array of events reported by webhook. | | null |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
