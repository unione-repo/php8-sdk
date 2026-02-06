# # ProjectAccountingObject

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**emailCounter** | **int** | Project&#39;s email counter value. It increases on every email sent. | | null |  true 
**emailCounterLimit** | **int** | Allows you to limit the number of emails sent by the project. The sending stops when the limit is reached. Any non-negative 64-bit integer is acceptable. 0 means no limit. | | null |  true 
**emailCounterMode** | **string** | &#39;default&#39; - the counter resets to zero automatically at the beginning of each accounting period. &#39;permanent&#39; - the counter never resets automatically. | [default to 'default'] | null |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
