# # WebhookObject

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**id** | **int** | Webhook unique identifier. | | null |  true 
**url** | **string** | Webhook URL. | | null |  true 
**status** | [**\UniOne\Model\WebhookStatusString**](WebhookStatusString.md) |  | | null |  true 
**eventFormat** | [**\UniOne\Model\WebhookEventFormatString**](WebhookEventFormatString.md) |  | | null |  true 
**deliveryInfo** | [**\UniOne\Model\WebhookDeliveryInfoInteger**](WebhookDeliveryInfoInteger.md) |  | | null |  true 
**singleEvent** | [**\UniOne\Model\WebhookSingleEventInteger**](WebhookSingleEventInteger.md) |  | | null |  true 
**maxParallel** | **int** | Maximum quantity of permitted parallel queries to your server. The more your server can handle - the better. | [default to 10] | null |  true 
**updatedAt** | **string** | Webhook properties last update date and time in UTC timezone in **YYYY-MM-DD hh:mm:ss** format. | | null | 
**events** | [**\UniOne\Model\WebhookEventsObject**](WebhookEventsObject.md) |  | | null | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
