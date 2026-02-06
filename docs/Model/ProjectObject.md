# # ProjectObject

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**name** | **string** | Project name, unique for user account. | | Project 1A |  true 
**country** | **string** | ISO-3166 alpha-2 country code. If set, UniOne treats project personal data according to country laws, e.g. GDPR for european countries. | | ES | 
**sendEnabled** | **bool** | Whether email sending is enabled for this project or not. | [default to true] | null | 
**customUnsubscribeUrlEnabled** | **bool** | If it&#39;s false then UniOne adds default unsubscribe footer to each email sent with API key of the project. If it&#39;s true then appending default unsubscribe footer for this project is avoided and sending with custom unsubscribe url or even without unsubscribe url is permitted for the project. Please note that custom_unsubscribe_url_enabled&#x3D;true is available only if removing unsubscribe link is approved for the user account by support. More on this [here](https://docs.unione.io/en/unsubscribe-link). When custom_unsubscribe_url_enabled is skipped on creating a project, it&#39;s value is taken from user | | null | 
**backendDomainId** | **int** | A unique domain identifier which will determine the [tracking domain](https://docs.unione.io/en/tracking-domains) or [dedicated IP](/dedicated-ip) pool to be used by default. If the value is not specified, a default backend domain will be assigned for your account or project instead. | | 1234 | 
**unsubscribePageId** | **int** | A unique identifier that defines the default unsubscribe page. If absent, the account/project will be assigned the system default unsubscribe page. | | 1 | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
