# # DomainList200ResponseDomainsInnerDkim

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**key** | **string** | DKIM signature for the domain. This property contains only the key part, you should prepend it with **k&#x3D;rsa, p&#x3D;** part for the record to be valid (see [domain/get-dns-records](https://docs.unione.io/en/web-api-ref#domain-get-dns-records)). | | MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDo7 | 
**status** | **string** | Only domains with **active** DKIM record are allowed as sender domains. | | null | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
