# # MessageObjectOptions

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**sendAt** | **string** | Date and time in **YYYY-MM-DD hh:mm:ss** format in the UTC timezone. Allows schedule sending up to 24 hours in advance. | | 2021-11-19 10:00:00 | 
**unsubscribeUrl** | **string** | Custom unsubscribe link. Read more [here](https://docs.unione.io/en/unsubscribe-link). | | https://example.org/unsubscribe/b;b;CustomerIdc;c; | 
**customBackendId** | **int** | Backend-domain identifier to send message with. If custom_backend_id is not set, default one for your account/project will be used. You can pay for one or more dedicated IPs and use this option. | | null | 
**smtpPoolId** | **string** | SMTP pool identifier to send message with. Usually you don&#39;t need to pass this parameter because correct smtp_pool_id is selected automatically based on the default one for your account/project or according to custom_backend_id parameter. | | null | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
