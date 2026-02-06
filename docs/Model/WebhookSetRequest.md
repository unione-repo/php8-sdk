# # WebhookSetRequest

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**url** | **string** | URL that will receive the notification when an event occurs. The URL should be unique for a user or a project. Only ASCII characters are supported for now in URL, please convert to [Punycode](https://en.wikipedia.org/wiki/Punycode) if you need to use non-ASCII characters. | | https://yourhost.example.com/unione-webhook |  true 
**status** | [**\UniOne\Model\WebhookStatusString**](WebhookStatusString.md) |  | | null | 
**eventFormat** | [**\UniOne\Model\WebhookEventFormatString**](WebhookEventFormatString.md) |  | | null | 
**deliveryInfo** | [**\UniOne\Model\WebhookDeliveryInfoInteger**](WebhookDeliveryInfoInteger.md) |  | | null | 
**singleEvent** | [**\UniOne\Model\WebhookSingleEventInteger**](WebhookSingleEventInteger.md) |  | | null | 
**maxParallel** | **int** | Maximum quantity of permitted parallel queries to your server. The more your server can handle - the better. | [default to 10] | null | 
**events** | [**\UniOne\Model\WebhookEventsObject**](WebhookEventsObject.md) |  | | null | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
