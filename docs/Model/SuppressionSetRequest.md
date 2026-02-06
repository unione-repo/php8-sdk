# # SuppressionSetRequest

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**email** | **string** | Email to add in suppression list. | | email@example.com |  true 
**cause** | **string** | Cause of email being suppressed. One of:&lt;br&gt;&lt;br&gt;* __unsubscribed__ - email is unsubscribed;* __temporary_unavailable__ - the email address is unavailable. This means that over the next three days sending to this address will return an error. Email may be temporarily unavailable due to several reasons, e.g.:&lt;br&gt;    1. a previous email has been rejected by the recipient&#39;s server for spam;* the recipient&#39;s mailbox is full or is not used;* recipient&#39;s domain does not accept mail;* sending server was rejected due to blacklisting;* __permanent_unavailable__ - the email address is permanently unavailable due to multiple hard bounces;* __complained__ - the recipient reported spam in the previous emails; | | unsubscribed |  true 
**created** | **string** | When suppression was created, in UTC timezone in **YYYY-MM-DD hh:mm:ss** format. | | 2021-12-19 10:15:49 | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
