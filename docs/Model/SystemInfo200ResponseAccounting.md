# # SystemInfo200ResponseAccounting

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**periodStart** | **string** | Date and time of accounting period start in UTC in **YYYY-MM-DD hh:mm:ss** format. | | 2016-08-29 09:12:33 |  true 
**periodEnd** | **string** | Date and time of accounting period end in UTC in **YYYY-MM-DD hh:mm:ss** format. | | 2016-09-29 09:12:33 |  true 
**emailsIncluded** | **int** | Number of emails included into accounting period. | | null |  true 
**emailsSent** | **int** | Number of emails sent during accounting period. Can be bigger than emails_included in case of overage. | | null |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
