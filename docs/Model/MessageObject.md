# # MessageObject

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**recipients** | [**\UniOne\Model\MessageObjectRecipientsInner[]**](MessageObjectRecipientsInner.md) | Contains recipient emails, substitutions(merge tags) and metadata. | | [{"email":"email@example.com","substitutions":{"tag":"value"},"metadata":{"key":"value"}}] |  true 
**templateId** | **string** | Optional identifier of the template that had been created by [template/set](https://docs.unione.io/en/web-api-ref#template-set) method. If template_id is passed then fields from the template are used instead of missed email/send parameters. E.g. if **body** parameter in email/send is omitted, **body** from template will be used. If **subject** in email/send is omitted, **subject** from template will be used. | | 00000000-0000-0000-0000-000000000000 | 
**tags** | **string[]** | An array of strings. The maximum string length is 50 characters. You can include up to 4 strings which must be unique. No more than 10 000 tags are allowed per project; if you try to add more, email/send will return an error. You may use tags to categorize emails by your own criteria, and they will be passed along by event-dump methods. | | [] | 
**skipUnsubscribe** | **int** | Whether to skip or not appending default unsubscribe footer. 1&#x3D;skip, 0&#x3D;append, default is 0. You should [ask support](https://cp.unione.io/en/support) to approve&lt;br&gt;usage of skip_unsubscribe&#x3D;1. [Read more](https://docs.unione.io/en/unsubscribe-link). | | 0 | 
**globalLanguage** | **string** | The language of the unsubscribe footer and unsubscribe page. Languages supported are: **be**, **de**, **en**, **es**, **fr**, **it**, **pl**, **pt**, **ru**, **ua**, **kz**. | | en | 
**templateEngine** | [**\UniOne\Model\TemplateEngineString**](TemplateEngineString.md) |  | | null | 
**globalSubstitutions** | **array<string,string>** | Object for passing the substitutions(merge tags) common for all recipients - e.g., company name. If the substitution names are duplicated in object **substitutions**, the values of the variables will be taken from the object **substitutions**. The substitutions can be used in the following parameters:&lt;br&gt;&lt;br&gt;* body.html* body.plaintext* body.amp* subject* from_name* options.unsubscribe_url&lt;br&gt;&lt;br&gt;A substitution name can consist from latin characeters, numbers and **_** symbol, and should start with the letter. | | null | 
**globalMetadata** | **array<string,string>** | Object for passing the metadata common for all the recipients, such as **key**: **value**. Max key quantity: 10. Max key length: 64 symbols. Max value length: 1024 symbols. The metadata is returned by [webhook](https://docs.unione.io/en/web-api-ref#webhook). To group single emails into a campaign, you can use the system key &#39;campaign_id&#39; with a value in the form of a non-negative decimal integer up to 128 bits or a UUID in the format &#39;c7703772-453e-4c77-a9ae-9a1b94051b5a&#39;. Incorrect values will be treated as &#39;0&#39;. | | null | 
**body** | [**\UniOne\Model\BodyObject**](BodyObject.md) |  | | null |  true 
**subject** | **string** | Email subject. | | UniOne test email |  true 
**fromEmail** | **string** | Sender&#39;s email. Required only if template_id parameter is empty. | | email@example.com | 
**fromName** | **string** | Sender&#39;s name. | | John Smith | 
**replyTo** | **string** | Optional Reply-To email (in case it&#39;s different to sender&#39;s email) | | email@example.com | 
**replyToName** | **string** | Optional Reply-To name (if reply_to email is specified and you want to display not only this email but also the name) | | John Smith | 
**trackLinks** | [**\UniOne\Model\TrackLinksInteger**](TrackLinksInteger.md) |  | | null | 
**trackRead** | [**\UniOne\Model\TrackReadInteger**](TrackReadInteger.md) |  | | null | 
**bypassGlobal** | [**\UniOne\Model\BypassGlobalInteger**](BypassGlobalInteger.md) |  | | null | 
**bypassUnavailable** | [**\UniOne\Model\BypassUnavailableInteger**](BypassUnavailableInteger.md) |  | | null | 
**bypassUnsubscribed** | [**\UniOne\Model\BypassUnsubscribedInteger**](BypassUnsubscribedInteger.md) |  | | null | 
**bypassComplained** | [**\UniOne\Model\BypassComplainedInteger**](BypassComplainedInteger.md) |  | | null | 
**idempotenceKey** | **string** | A string of up to 64 characters containing a unique message key. This can be used to prevent occasional message duplicates. If you send another API request with the same message key within the next minute, it will be declined. We can generate a message key for each letter automatically; to enable this option, please contact our [tech support](https://cp.unione.io/en/support). | | SG1VsbG68sIH2dvc5mx890kIQ | 
**headers** | [**\UniOne\Model\HeadersObject**](HeadersObject.md) |  | | null | 
**attachments** | [**\UniOne\Model\AttachmentsArrayInner[]**](AttachmentsArrayInner.md) | Optional array of attachments | | null | 
**inlineAttachments** | [**\UniOne\Model\InlineAttachmentsArrayInner[]**](InlineAttachmentsArrayInner.md) | Optional array of inline attachments, e.g. for including images in email instead of loading them from external URL. | | null | 
**options** | [**\UniOne\Model\MessageObjectOptions**](MessageObjectOptions.md) |  | | null | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
