# # DomainGetDnsRecords200Response

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**status** | [**\UniOne\Model\SuccessStatusString**](SuccessStatusString.md) |  | | null |  true 
**domain** | **string** | Domain to get DNS records for. | | example.com |  true 
**verificationRecord** | **string** | Record to be added **as is** to verify ownership of this domain. | | unione-validate-hash=483bb362ebdbeedd755cfb1d4d661 |  true 
**dkim** | **string** | DKIM signature for the domain. This property contains only the key part, you should prepend it with **k&#x3D;rsa, p&#x3D;** part for the record to be valid (see example). | | MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDo7 |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
