# # SuppressionListRequest

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**cause** | **string** | Cause of email being suppressed. One of:&lt;br&gt;&lt;br&gt;* __unsubscribed__ - email is unsubscribed;* __temporary_unavailable__ - the email address is unavailable. This means that over the next three days sending to this address will return an error. Email may be temporarily unavailable due to several reasons, e.g.:&lt;br&gt;    1. a previous email has been rejected by the recipient&#39;s server for spam;* the recipient&#39;s mailbox is full or is not used;* recipient&#39;s domain does not accept mail;* sending server was rejected due to blacklisting;* __permanent_unavailable__ - the email address is permanently unavailable due to multiple hard bounces;* __complained__ - the recipient reported spam in the previous emails;* __blocked__ - sending to the email is prohibited by administration of UniOne.&lt;br&gt;&lt;br&gt;We may add some new causes in the future. | | unsubscribed | 
**source** | **string** | Source of email being suppressed. One of:&lt;br&gt;&lt;br&gt;* __user__ - suppressed by user with [suppression/set](https://docs.unione.io/en/web-api-ref#suppression-set);* __system__ - sending to the email is prohibited by system, for example due to multiple hard bounces;* __subscriber__ - the recipient reported spam or unsubscribed in the previous emails. | | user | 
**startTime** | **string** | Date in the format YYYY-MM-DD hh:mm:ss to get suppression list from the **start_time** to the present day. Ignored if **cursor** is not empty. | | 2020-10-14 17:00:00 | 
**cursor** | **string** | The parameter indicates from which position the selection is to be started. Must be empty or omitted for the first data chunk. In order to get subsequent chunks, you must set the **cursor** parameter in your request, using the value received in response to the previous request. | | Ajfb6Hvdkn3hdhhvG57xbdufhG5 | 
**limit** | **int** | Limits the number of records to be returned at one time, default is 50. | | 50 | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
