# # WebhookEventsObject

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**spamBlock** | **string[]** | If present then spam block events will be reported. Should contain single array element with ***** string. | | ["*"] | 
**emailStatus** | **string[]** | If present then email status change events will be reported. Contains names of statuses to notify of. | | ["delivered","opened","clicked","unsubscribed","subscribed","soft_bounced","hard_bounced","spam"] | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
