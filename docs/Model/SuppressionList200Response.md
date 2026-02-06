# # SuppressionList200Response

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**status** | [**\UniOne\Model\SuccessStatusString**](SuccessStatusString.md) |  | | null |  true 
**suppressions** | [**\UniOne\Model\SuppressionListObject[]**](SuppressionListObject.md) | Array of suppression objects. | | null |  true 
**cursor** | **string** | The parameter indicates from which position the selection is to be started. Must be empty or omitted for the first data chunk. In order to get subsequent chunks, you must set the **cursor** parameter in your request, using the value received in response to the previous request. | | Ajfb6Hvdkn3hdhhvG57xbdufhG5 |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
