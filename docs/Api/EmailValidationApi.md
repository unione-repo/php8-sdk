# UniOne\EmailValidationApi

All URIs are relative to https://api.unione.io/en/transactional/api/v1

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**emailValidationSingle()**](EmailValidationApi.md#emailValidationSingle) | **POST** /email-validation/single.json | A maximum of two concurrent requests are allowed; if you send more requests, an error will be returned. Since the verification process should be completed promptly, we&#39;ve set a time limit on email check. If we encounter a slow email server that does not respond in 5 seconds, you may get an “unknown” status. |


## `emailValidationSingle()`

```php
emailValidationSingle($emailValidationSingleRequest): \UniOne\Model\EmailValidationSingle200Response
```

A maximum of two concurrent requests are allowed; if you send more requests, an error will be returned. Since the verification process should be completed promptly, we've set a time limit on email check. If we encounter a slow email server that does not respond in 5 seconds, you may get an “unknown” status.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\EmailValidationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$emailValidationSingleRequest = new \UniOne\Model\EmailValidationSingleRequest();
$emailValidationSingleRequest
    ->setEmail('email@example.com');

try {
    $result = $apiInstance->emailValidationSingle($emailValidationSingleRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EmailValidationApi->emailValidationSingle: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **emailValidationSingleRequest** | [**\UniOne\Model\EmailValidationSingleRequest**](../Model/EmailValidationSingleRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\EmailValidationSingle200Response**](../Model/EmailValidationSingle200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
