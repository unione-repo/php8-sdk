# # WebhookSetJsonPostRequest

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**auth** | **string** | MD5-hash of the message body, in which the value **auth** is replaced by api key of the user/project; with this field the recipient of the notification can both authenticate and verify the notification integrity | | null |  true 
**eventsByUser** | [**\UniOne\Model\WebhookSetJsonPostRequestEventsByUserInner[]**](WebhookSetJsonPostRequestEventsByUserInner.md) | Array with only one element, containing events of a user/project. | | null |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
