# UniOne\EmailApi

All URIs are relative to https://api.unione.io/en/transactional/api/v1

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**emailSend()**](EmailApi.md#emailSend) | **POST** /email/send.json | Sends an email or a bunch of emails |
| [**emailSubscribe()**](EmailApi.md#emailSubscribe) | **POST** /email/subscribe.json | Sends an email with (re)subscribe link. |


## `emailSend()`

```php
emailSend($emailSendRequest): \UniOne\Model\EmailSend200Response
```

Sends an email or a bunch of emails

While sending you can provide substitutions (merge tags), use a template, turn on read or click tracking, etc.<br>Restrictions:<br>* maximum request size is 10 MB<br>* maximum number of recipients is 500<br>* The symbol '/' is not allowed in attachment names<br>If the list of recipients contains invalid, non-existent, duplicate, or unsubscribed emails, those emails will be returned in the output parameter failed_emails, and the email will be sent to all other valid emails addresses. If all the emails addresses fall into failed_emails, sending will not be carried out and API error 204 will be returned.

### Example

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

$emailSendRequest = new \UniOne\Model\EmailSendRequest();
$emailSendRequest
    ->setMessage((new \UniOne\Model\MessageObject());

try {
    $result = $apiInstance->emailSend($emailSendRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EmailApi->emailSend: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **emailSendRequest** | [**\UniOne\Model\EmailSendRequest**](../Model/EmailSendRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\EmailSend200Response**](../Model/EmailSend200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `emailSubscribe()`

```php
emailSubscribe($emailSubscribeRequest): \UniOne\Model\SuccessResponse
```

Sends an email with (re)subscribe link.

This method allows subscription renewal by a former subscriber who has previously unsubscribed, or who is blocked because of complaints. This method sends an email with a new subscription link to a former subscriber. Once the recipient clicks the link, their subscription status is restored.<br>There is a default restriction that limits this method to being used once a day. If you need to resubscribe more often, please ask support about it.

### Example

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

$emailSubscribeRequest = new \UniOne\Model\EmailSubscribeRequest();
$emailSubscribeRequest
    ->setFromEmail('email@example.com')
    ->setFromName('Example')
    ->setToEmail('email@example.com');

try {
    $result = $apiInstance->emailSubscribe($emailSubscribeRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EmailApi->emailSubscribe: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **emailSubscribeRequest** | [**\UniOne\Model\EmailSubscribeRequest**](../Model/EmailSubscribeRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\SuccessResponse**](../Model/SuccessResponse.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
