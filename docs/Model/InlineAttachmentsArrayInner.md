# # InlineAttachmentsArrayInner

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**type** | **string** | Attachment type, see [MIME](https://en.wikipedia.org/wiki/MIME). If unsure, use **application/octet-stream**. | | image/gif |  true 
**name** | **string** | Attachment content id. For example, **name**&#x3D;**IMAGECID1** should be referenced in HTML like &lt;img src&#x3D;**cid:IMAGECID1**&gt;. | | IMAGECID1 |  true 
**content** | **string** | File contents in [base64](https://en.wikipedia.org/wiki/Base64). Maximum file size 7MB (9786710 bytes in base64). | | [B@26c77f54 |  true 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
