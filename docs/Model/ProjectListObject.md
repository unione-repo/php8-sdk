# # ProjectListObject

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**id** | **string** | Unqiue project identifier, ASCII string up to 36 characters long. | | 6123462132634 |  true 
**apiKey** | **string** | API key of the project. You can use it instead of the user API key parameter in all methods except project/_* methods. | | null |  true 
**name** | **string** | Project name, unique for user account. | | Project 1A |  true 
**country** | **string** | ISO-3166 alpha-2 country code. If set, UniOne treats project personal data according to country laws, e.g. GDPR for european countries. | | ES |  true 
**regTime** | **string** | Date and time of project creation in UTC timezone in **YYYY-MM-DD hh:mm:ss** format. | | 2020-12-28 17:15:45 |  true 
**sendEnabled** | **bool** | Whether email sending is enabled for this project or not. | [default to true] | null |  true 
**customUnsubscribeUrlEnabled** | **bool** | If it&#39;s false then UniOne adds default unsubscribe footer to each email sent with API key of the project. If it&#39;s true then appending default unsubscribe footer for this project is avoided and sending with custom unsubscribe url or even without unsubscribe url is permitted for the project. Please note that custom_unsubscribe_url_enabled&#x3D;true is available only if removing unsubscribe link is approved for the user account by support. More on this [here](https://docs.unione.io/en/unsubscribe-link). When custom_unsubscribe_url_enabled is skipped on creating a project, it&#39;s value is taken from user | | null |  true 
**backendDomainId** | **int** | A unique domain identifier which will determine the [tracking domain](https://docs.unione.io/en/tracking-domains) or [dedicated IP](/dedicated-ip) pool to be used by default. If the value is not specified, a default backend domain will be assigned for your account or project instead. | | 1234 |  true 
**emailCounter** | **int** | Project&#39;s email counter value. It increases on every email sent. | | null |  true 
**emailCounterLimit** | **int** | Allows you to limit the number of emails sent by the project. The sending stops when the limit is reached. Any non-negative 64-bit integer is acceptable. 0 means no limit. | | null |  true 
**emailCounterMode** | **string** | &#39;default&#39; - the counter resets to zero automatically at the beginning of each accounting period. &#39;permanent&#39; - the counter never resets automatically. | [default to 'default'] | null |  true 
**unsubscribePageId** | **int** | A unique identifier that defines the default unsubscribe page. If absent, the account/project will be assigned the system default unsubscribe page. | | 1 |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
