# # TemplateListObject

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**id** | **string** | Template unique identifier. | | null |  true 
**name** | **string** | Template name. | | null |  true 
**editorType** | [**\UniOne\Model\EditorTypeString**](EditorTypeString.md) |  | | null | 
**templateEngine** | [**\UniOne\Model\TemplateEngineString**](TemplateEngineString.md) |  | | null | 
**globalSubstitutions** | **array<string,string>** | Object for passing the substitutions(merge tags) common for all recipients - e.g., company name. If the substitution names are duplicated in object **substitutions**, the values of the variables will be taken from the object **substitutions**. The substitutions can be used in the following parameters:&lt;br&gt;&lt;br&gt;* body.html* body.plaintext* body.amp* subject* from_name* options.unsubscribe_url&lt;br&gt;&lt;br&gt;A substitution name can consist from latin characeters, numbers and **_** symbol, and should start with the letter. | | null | 
**globalMetadata** | **array<string,string>** | Object for passing the metadata common for all the recipients, such as **key**: **value**. Max key quantity: 10. Max key length: 64 symbols. Max value length: 1024 symbols. The metadata is returned by [webhook](https://docs.unione.io/en/web-api-ref#webhook). To group single emails into a campaign, you can use the system key &#39;campaign_id&#39; with a value in the form of a non-negative decimal integer up to 128 bits or a UUID in the format &#39;c7703772-453e-4c77-a9ae-9a1b94051b5a&#39;. Incorrect values will be treated as &#39;0&#39;. | | null | 
**body** | [**\UniOne\Model\BodyObject**](BodyObject.md) |  | | null |  true 
**subject** | **string** | Email subject. | | UniOne test email | 
**fromEmail** | **string** | Sender&#39;s email. | | null |  true 
**fromName** | **string** | Sender&#39;s name. | | John Smith | 
**replyTo** | **string** | Optional Reply-To email (in case it&#39;s different to sender&#39;s email) | | email@example.com | 
**replyToName** | **string** | Optional Reply-To name (if reply_to email is specified and you want to display not only this email but also the name) | | John Smith | 
**trackLinks** | [**\UniOne\Model\TrackLinksInteger**](TrackLinksInteger.md) |  | | null | 
**trackRead** | [**\UniOne\Model\TrackReadInteger**](TrackReadInteger.md) |  | | null | 
**headers** | [**\UniOne\Model\HeadersObject**](HeadersObject.md) |  | | null | 
**attachments** | [**\UniOne\Model\AttachmentsArrayInner[]**](AttachmentsArrayInner.md) | Optional array of attachments | | null | 
**inlineAttachments** | [**\UniOne\Model\InlineAttachmentsArrayInner[]**](InlineAttachmentsArrayInner.md) | Optional array of inline attachments, e.g. for including images in email instead of loading them from external URL. | | null | 
**created** | **string** | Template creation date and time in UTC timezone in format **YYYY-MM-DD hh:mm:ss** | | null |  true 
**userId** | **int** | Unique user identifier. | | 11344 |  true 
**projectId** | **string** | Unqiue project identifier, ASCII string up to 36 characters long. | | 6123462132634 | 
**projectName** | **string** | Project name, unique for user account. | | Project 1A | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
