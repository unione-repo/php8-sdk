# php8-sdk

All UniOne API methods require HTTPS connection. UniOne accepts HTTP POST requests in JSON format up to 10 megabytes long and returns HTTP response also in JSON. API endpoint (or base URL) depends on which datacenter the user is registered at.<br>You can use https://eu1.unione.io/en/transactional/api/v1 or https://us1.unione.io/en/transactional/api/v1 directly.

For more information, please visit [https://cp.unione.io/en/support](https://cp.unione.io/en/support).

## Installation & Usage

### Requirements

PHP 8.1 and later.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/unione-repo/php8-sdk.git"
    }
  ],
  "require": {
    "unione-repo/php8-sdk": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/php8-sdk/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');

$apiInstance = new UniOne\Api\EmailApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$bodyObject = new \UniOne\Model\BodyObject();
$bodyObject
    ->setHtml("<b>Hello, {{to_name}}</b>");

$messageObject = new \UniOne\Model\MessageObject();
$messageObject
    ->setSubject("UniOne test email")
    ->setFromEmail("user@example.com")
    ->setRecipients([{"email":"email@example.com","substitutions":{"to_name":"John Smith"},"metadata":{"campaign_id":"c77f4f4e-3561-49f7-9f07-c35be01b4f43"}}])
    ->setBody($bodyObject);

$emailSendRequest = new \UniOne\Model\EmailSendRequest();
$emailSendRequest
    ->setMessage($messageObject);

try {
    $result = $apiInstance->emailSend($emailSendRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EmailApi->emailSend: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to https://api.unione.io/en/transactional/api/v1

        ### URI(s):
    - https://api.unione.io/en/transactional/api/v1 UniOne API-server instance


Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*DomainApi* | [**domainDelete**](docs/Api/DomainApi.md#domaindelete) | **POST** /domain/delete.json | Deletes a domain. Attention: you should use project&#39;s API key to delete a project&#39;s domain.
*DomainApi* | [**domainGetDnsRecords**](docs/Api/DomainApi.md#domaingetdnsrecords) | **POST** /domain/get-dns-records.json | Returns info on domain DNS setup for using with UniOne.
*DomainApi* | [**domainList**](docs/Api/DomainApi.md#domainlist) | **POST** /domain/list.json | Returns a list of all registered domains for user or project, together with statuses of last validations.
*DomainApi* | [**domainValidateDkim**](docs/Api/DomainApi.md#domainvalidatedkim) | **POST** /domain/validate-dkim.json | Validates DKIM record for domain.
*DomainApi* | [**domainValidateVerificationRecord**](docs/Api/DomainApi.md#domainvalidateverificationrecord) | **POST** /domain/validate-verification-record.json | Triggers verification record validation for domain.
*EmailApi* | [**emailSend**](docs/Api/EmailApi.md#emailsend) | **POST** /email/send.json | Sends an email or a bunch of emails
*EmailApi* | [**emailSubscribe**](docs/Api/EmailApi.md#emailsubscribe) | **POST** /email/subscribe.json | Sends an email with (re)subscribe link.
*EmailValidationApi* | [**emailValidationSingle**](docs/Api/EmailValidationApi.md#emailvalidationsingle) | **POST** /email-validation/single.json | A maximum of two concurrent requests are allowed; if you send more requests, an error will be returned. Since the verification process should be completed promptly, we&#39;ve set a time limit on email check. If we encounter a slow email server that does not respond in 5 seconds, you may get an “unknown” status.
*EventDumpApi* | [**eventDumpCreate**](docs/Api/EventDumpApi.md#eventdumpcreate) | **POST** /event-dump/create.json | This asynchronous method initiates the preparation of data dump in CSV format. The number of dump files created or stored is limited to 10; to order more files, you have to delete one of the previous ones or wait until they will be deleted automatically. A newly created dump file is kept for 8 hours. If the request period is more than a day or there are too many events then several files will be generated and each file will contain no more than 100,000 events. File contains columns with the following information - &#39;event_time&#39;, &#39;job_id&#39;, &#39;from_email&#39;, &#39;email&#39;, &#39;status&#39;, &#39;delivery_status&#39;, &#39;metadata&#39;, &#39;destination_response&#39;, &#39;user_agent&#39;, &#39;url&#39;, &#39;ip&#39;, &#39;tags&#39; and &#39;project_id&#39; (for accounts with projects enabled). You can change the fields and include &#39;subject&#39; field using &#39;dump_fileds&#39; parameter.
*EventDumpApi* | [**eventDumpDelete**](docs/Api/EventDumpApi.md#eventdumpdelete) | **POST** /event-dump/delete.json | Removes dump from queue or storage.
*EventDumpApi* | [**eventDumpGet**](docs/Api/EventDumpApi.md#eventdumpget) | **POST** /event-dump/get.json | Returns dump properties for a given identifier
*EventDumpApi* | [**eventDumpList**](docs/Api/EventDumpApi.md#eventdumplist) | **POST** /event-dump/list.json | This method does not require any parameters; returns the full list of existing dumps.
*ObsoleteApi* | [**unsubscribedCheck**](docs/Api/ObsoleteApi.md#unsubscribedcheck) | **POST** /unsubscribed/check.json | Checks if an email is unsubscribed.
*ObsoleteApi* | [**unsubscribedList**](docs/Api/ObsoleteApi.md#unsubscribedlist) | **POST** /unsubscribed/list.json | Returns a list of all unsubscribed emails since provided date.
*ObsoleteApi* | [**unsubscribedSet**](docs/Api/ObsoleteApi.md#unsubscribedset) | **POST** /unsubscribed/set.json | Registers a new unsubscribed email.
*ProjectApi* | [**projectCreate**](docs/Api/ProjectApi.md#projectcreate) | **POST** /project/create.json | Creates a new project.
*ProjectApi* | [**projectDelete**](docs/Api/ProjectApi.md#projectdelete) | **POST** /project/delete.json | Deletes a project.
*ProjectApi* | [**projectList**](docs/Api/ProjectApi.md#projectlist) | **POST** /project/list.json | Lists projects.
*ProjectApi* | [**projectUpdate**](docs/Api/ProjectApi.md#projectupdate) | **POST** /project/update.json | Updates a project.
*SuppressionApi* | [**suppressionDelete**](docs/Api/SuppressionApi.md#suppressiondelete) | **POST** /suppression/delete.json | Deletes an email from suppression list (only records with is_deletable&#x3D;true). If there are no entries of this email in the suppression list, API error 3003 is returned. If such entries exist but no one can be deleted, API error 3004 is returned. If daily limit of deletes exceeded, API error 906 is returned.
*SuppressionApi* | [**suppressionGet**](docs/Api/SuppressionApi.md#suppressionget) | **POST** /suppression/get.json | Gets a reason and date of email suppression.
*SuppressionApi* | [**suppressionList**](docs/Api/SuppressionApi.md#suppressionlist) | **POST** /suppression/list.json | Returns a suppression list since provided date.
*SuppressionApi* | [**suppressionSet**](docs/Api/SuppressionApi.md#suppressionset) | **POST** /suppression/set.json | Adds an email address to the suppression list. You can always remove this address from the suppression list later using the [suppression/delete](https://docs.unione.io/en/web-api-ref#suppression-delete) method.
*SystemApi* | [**systemInfo**](docs/Api/SystemApi.md#systeminfo) | **POST** /system/info.json | Gets user or project info by API key.
*TagApi* | [**tagDelete**](docs/Api/TagApi.md#tagdelete) | **POST** /tag/delete.json | Removes tag.
*TagApi* | [**tagList**](docs/Api/TagApi.md#taglist) | **POST** /tag/list.json | This method returns the full list of user-defined tags. Does not receive any parameters.
*TemplateApi* | [**templateDelete**](docs/Api/TemplateApi.md#templatedelete) | **POST** /template/delete.json | Deletes a template by id.
*TemplateApi* | [**templateGet**](docs/Api/TemplateApi.md#templateget) | **POST** /template/get.json | Gets template properties by it&#39;s id.
*TemplateApi* | [**templateList**](docs/Api/TemplateApi.md#templatelist) | **POST** /template/list.json | Returns the list of all or some templates of the account.
*TemplateApi* | [**templateSet**](docs/Api/TemplateApi.md#templateset) | **POST** /template/set.json | Creates or updates an email template.
*WebhookApi* | [**webhookDelete**](docs/Api/WebhookApi.md#webhookdelete) | **POST** /webhook/delete.json | Deletes an event notification handler
*WebhookApi* | [**webhookGet**](docs/Api/WebhookApi.md#webhookget) | **POST** /webhook/get.json | Gets properties of a [webhook](https://docs.unione.io/en/web-api-ref#webhook).
*WebhookApi* | [**webhookList**](docs/Api/WebhookApi.md#webhooklist) | **POST** /webhook/list.json | List all or some [webhooks](https://docs.unione.io/en/web-api-ref#webhook) (event notification handlers) of a user or a project.
*WebhookApi* | [**webhookSet**](docs/Api/WebhookApi.md#webhookset) | **POST** /webhook/set.json | Sets or edits a [webhook](https://docs.unione.io/en/web-api-ref#webhook), i.e. an event notification handler.

## Models

- [AttachmentsArrayInner](docs/Model/AttachmentsArrayInner.md)
- [BodyObject](docs/Model/BodyObject.md)
- [BypassComplainedInteger](docs/Model/BypassComplainedInteger.md)
- [BypassGlobalInteger](docs/Model/BypassGlobalInteger.md)
- [BypassUnavailableInteger](docs/Model/BypassUnavailableInteger.md)
- [BypassUnsubscribedInteger](docs/Model/BypassUnsubscribedInteger.md)
- [DomainDelete200Response](docs/Model/DomainDelete200Response.md)
- [DomainDeleteRequest](docs/Model/DomainDeleteRequest.md)
- [DomainGetDnsRecords200Response](docs/Model/DomainGetDnsRecords200Response.md)
- [DomainGetDnsRecordsRequest](docs/Model/DomainGetDnsRecordsRequest.md)
- [DomainList200Response](docs/Model/DomainList200Response.md)
- [DomainList200ResponseDomainsInner](docs/Model/DomainList200ResponseDomainsInner.md)
- [DomainList200ResponseDomainsInnerDkim](docs/Model/DomainList200ResponseDomainsInnerDkim.md)
- [DomainList200ResponseDomainsInnerVerificationRecord](docs/Model/DomainList200ResponseDomainsInnerVerificationRecord.md)
- [DomainListRequest](docs/Model/DomainListRequest.md)
- [DomainValidateDkimRequest](docs/Model/DomainValidateDkimRequest.md)
- [DomainValidateVerificationRecord200Response](docs/Model/DomainValidateVerificationRecord200Response.md)
- [DomainValidateVerificationRecordRequest](docs/Model/DomainValidateVerificationRecordRequest.md)
- [EditorTypeString](docs/Model/EditorTypeString.md)
- [EmailSend200Response](docs/Model/EmailSend200Response.md)
- [EmailSendRequest](docs/Model/EmailSendRequest.md)
- [EmailSubscribeRequest](docs/Model/EmailSubscribeRequest.md)
- [EmailValidationSingle200Response](docs/Model/EmailValidationSingle200Response.md)
- [EmailValidationSingleRequest](docs/Model/EmailValidationSingleRequest.md)
- [ErrorResponse](docs/Model/ErrorResponse.md)
- [EventDumpCreate200Response](docs/Model/EventDumpCreate200Response.md)
- [EventDumpCreateRequest](docs/Model/EventDumpCreateRequest.md)
- [EventDumpDeleteRequest](docs/Model/EventDumpDeleteRequest.md)
- [EventDumpFilesObject](docs/Model/EventDumpFilesObject.md)
- [EventDumpGet200Response](docs/Model/EventDumpGet200Response.md)
- [EventDumpGetRequest](docs/Model/EventDumpGetRequest.md)
- [EventDumpList200Response](docs/Model/EventDumpList200Response.md)
- [EventDumpObject](docs/Model/EventDumpObject.md)
- [FilterObject](docs/Model/FilterObject.md)
- [HeadersObject](docs/Model/HeadersObject.md)
- [InlineAttachmentsArrayInner](docs/Model/InlineAttachmentsArrayInner.md)
- [MessageObject](docs/Model/MessageObject.md)
- [MessageObjectOptions](docs/Model/MessageObjectOptions.md)
- [MessageObjectRecipientsInner](docs/Model/MessageObjectRecipientsInner.md)
- [ProjectAccountingObject](docs/Model/ProjectAccountingObject.md)
- [ProjectCreate200Response](docs/Model/ProjectCreate200Response.md)
- [ProjectCreateRequest](docs/Model/ProjectCreateRequest.md)
- [ProjectDeleteRequest](docs/Model/ProjectDeleteRequest.md)
- [ProjectList200Response](docs/Model/ProjectList200Response.md)
- [ProjectListObject](docs/Model/ProjectListObject.md)
- [ProjectListRequest](docs/Model/ProjectListRequest.md)
- [ProjectObject](docs/Model/ProjectObject.md)
- [ProjectUpdate200Response](docs/Model/ProjectUpdate200Response.md)
- [ProjectUpdateObject](docs/Model/ProjectUpdateObject.md)
- [ProjectUpdateRequest](docs/Model/ProjectUpdateRequest.md)
- [SuccessResponse](docs/Model/SuccessResponse.md)
- [SuccessStatusString](docs/Model/SuccessStatusString.md)
- [SuppressionDeleteRequest](docs/Model/SuppressionDeleteRequest.md)
- [SuppressionGet200Response](docs/Model/SuppressionGet200Response.md)
- [SuppressionGetObject](docs/Model/SuppressionGetObject.md)
- [SuppressionGetRequest](docs/Model/SuppressionGetRequest.md)
- [SuppressionList200Response](docs/Model/SuppressionList200Response.md)
- [SuppressionListObject](docs/Model/SuppressionListObject.md)
- [SuppressionListRequest](docs/Model/SuppressionListRequest.md)
- [SuppressionSetRequest](docs/Model/SuppressionSetRequest.md)
- [SystemInfo200Response](docs/Model/SystemInfo200Response.md)
- [SystemInfo200ResponseAccounting](docs/Model/SystemInfo200ResponseAccounting.md)
- [TagDeleteRequest](docs/Model/TagDeleteRequest.md)
- [TagList200Response](docs/Model/TagList200Response.md)
- [TagsResponseObject](docs/Model/TagsResponseObject.md)
- [TemplateEngineString](docs/Model/TemplateEngineString.md)
- [TemplateGetRequest](docs/Model/TemplateGetRequest.md)
- [TemplateList200Response](docs/Model/TemplateList200Response.md)
- [TemplateListObject](docs/Model/TemplateListObject.md)
- [TemplateListRequest](docs/Model/TemplateListRequest.md)
- [TemplateObject](docs/Model/TemplateObject.md)
- [TemplateSet200Response](docs/Model/TemplateSet200Response.md)
- [TemplateSetRequest](docs/Model/TemplateSetRequest.md)
- [TrackLinksInteger](docs/Model/TrackLinksInteger.md)
- [TrackReadInteger](docs/Model/TrackReadInteger.md)
- [UnsubscribedCheck200Response](docs/Model/UnsubscribedCheck200Response.md)
- [UnsubscribedCheckRequest](docs/Model/UnsubscribedCheckRequest.md)
- [UnsubscribedList200Response](docs/Model/UnsubscribedList200Response.md)
- [UnsubscribedList200ResponseUnsubscribedInner](docs/Model/UnsubscribedList200ResponseUnsubscribedInner.md)
- [UnsubscribedListRequest](docs/Model/UnsubscribedListRequest.md)
- [UnsubscribedSet200Response](docs/Model/UnsubscribedSet200Response.md)
- [UnsubscribedSetRequest](docs/Model/UnsubscribedSetRequest.md)
- [WebhookDeliveryInfoInteger](docs/Model/WebhookDeliveryInfoInteger.md)
- [WebhookEventFormatString](docs/Model/WebhookEventFormatString.md)
- [WebhookEventsObject](docs/Model/WebhookEventsObject.md)
- [WebhookGetRequest](docs/Model/WebhookGetRequest.md)
- [WebhookList200Response](docs/Model/WebhookList200Response.md)
- [WebhookListRequest](docs/Model/WebhookListRequest.md)
- [WebhookObject](docs/Model/WebhookObject.md)
- [WebhookSet200Response](docs/Model/WebhookSet200Response.md)
- [WebhookSetJsonPostRequest](docs/Model/WebhookSetJsonPostRequest.md)
- [WebhookSetJsonPostRequestEventsByUserInner](docs/Model/WebhookSetJsonPostRequestEventsByUserInner.md)
- [WebhookSetJsonPostRequestEventsByUserInnerEventsInner](docs/Model/WebhookSetJsonPostRequestEventsByUserInnerEventsInner.md)
- [WebhookSetJsonPostRequestEventsByUserInnerEventsInnerEventData](docs/Model/WebhookSetJsonPostRequestEventsByUserInnerEventsInnerEventData.md)
- [WebhookSetJsonPostRequestEventsByUserInnerEventsInnerEventDataDeliveryInfo](docs/Model/WebhookSetJsonPostRequestEventsByUserInnerEventsInnerEventDataDeliveryInfo.md)
- [WebhookSetRequest](docs/Model/WebhookSetRequest.md)
- [WebhookSingleEventInteger](docs/Model/WebhookSingleEventInteger.md)
- [WebhookStatusString](docs/Model/WebhookStatusString.md)

## Authorization

### apiKeyAuth

- **Type**: API key
- **API key parameter name**: X-API-KEY
- **Location**: HTTP header


## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author



## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.76`
    - Package version: `1.0.0`
    - Generator version: `7.19.0`
- Build package: `org.openapitools.codegen.languages.PhpNextgenClientCodegen`
