# # SystemInfo200Response

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**status** | [**\UniOne\Model\SuccessStatusString**](SuccessStatusString.md) |  | | null |  true 
**userId** | **int** | Unique user identifier. | | 11344 |  true 
**email** | **string** | Email of the user. | | null |  true 
**projectId** | **string** | Unqiue project identifier, ASCII string up to 36 characters long. Present only if the API key used for request is the project API key. | | 6123462132634 | 
**projectName** | **string** | Project name, unique for user account. Present only if the API key used for request is the project API key. | | Project 1A | 
**projectAccounting** | [**\UniOne\Model\ProjectAccountingObject**](ProjectAccountingObject.md) |  | | null | 
**accounting** | [**\UniOne\Model\SystemInfo200ResponseAccounting**](SystemInfo200ResponseAccounting.md) |  | | null | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
