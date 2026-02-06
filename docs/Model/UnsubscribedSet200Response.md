# # UnsubscribedSet200Response

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**status** | [**\UniOne\Model\SuccessStatusString**](SuccessStatusString.md) |  | | null |  true 
**address** | **string** | The unsubscribed email. | | null |  true 
**message** | **string** | Unsubscription process details:&lt;br&gt;&lt;br&gt;* **unsubscribed** if email has just been unsubscribed,* **was inactive** if it was inactive due some reason,* **was unsubscribed** if it already was unsubscribed before the call,* **added and unsubscribed** if it&#39;s a new email without status history and it was added and then unsubscribed immediately. | | null |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
