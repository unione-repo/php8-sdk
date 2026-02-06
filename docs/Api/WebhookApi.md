# UniOne\WebhookApi

All URIs are relative to https://api.unione.io/en/transactional/api/v1

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**webhookDelete()**](WebhookApi.md#webhookDelete) | **POST** /webhook/delete.json | Deletes an event notification handler |
| [**webhookGet()**](WebhookApi.md#webhookGet) | **POST** /webhook/get.json | Gets properties of a [webhook](https://docs.unione.io/en/web-api-ref#webhook). |
| [**webhookList()**](WebhookApi.md#webhookList) | **POST** /webhook/list.json | List all or some [webhooks](https://docs.unione.io/en/web-api-ref#webhook) (event notification handlers) of a user or a project. |
| [**webhookSet()**](WebhookApi.md#webhookSet) | **POST** /webhook/set.json | Sets or edits a [webhook](https://docs.unione.io/en/web-api-ref#webhook), i.e. an event notification handler. |


## `webhookDelete()`

```php
webhookDelete($webhookGetRequest): \UniOne\Model\SuccessResponse
```

Deletes an event notification handler

You can also temporarily deactivate webhook without deleting it by setting it's status to **disabled** in [webhook/set](https://docs.unione.io/en/web-api-ref#webhook-set) method.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\WebhookApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$webhookGetRequest = new \UniOne\Model\WebhookGetRequest();
$webhookGetRequest
    ->setUrl('https://example.com/webhook');

try {
    $result = $apiInstance->webhookDelete($webhookGetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhookApi->webhookDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **webhookGetRequest** | [**\UniOne\Model\WebhookGetRequest**](../Model/WebhookGetRequest.md)|  | |  true 

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

## `webhookGet()`

```php
webhookGet($webhookGetRequest): \UniOne\Model\WebhookSet200Response
```

Gets properties of a [webhook](https://docs.unione.io/en/web-api-ref#webhook).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\WebhookApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$webhookGetRequest = new \UniOne\Model\WebhookGetRequest();
$webhookGetRequest
    ->setUrl('https://example.com/webhook');

try {
    $result = $apiInstance->webhookGet($webhookGetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhookApi->webhookGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **webhookGetRequest** | [**\UniOne\Model\WebhookGetRequest**](../Model/WebhookGetRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\WebhookSet200Response**](../Model/WebhookSet200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `webhookList()`

```php
webhookList($webhookListRequest): \UniOne\Model\WebhookList200Response
```

List all or some [webhooks](https://docs.unione.io/en/web-api-ref#webhook) (event notification handlers) of a user or a project.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\WebhookApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$webhookListRequest = new \UniOne\Model\WebhookListRequest();
$webhookListRequest
    ->setLimit(null)
    ->setOffset(null);

try {
    $result = $apiInstance->webhookList($webhookListRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhookApi->webhookList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **webhookListRequest** | [**\UniOne\Model\WebhookListRequest**](../Model/WebhookListRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\WebhookList200Response**](../Model/WebhookList200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `webhookSet()`

```php
webhookSet($webhookSetRequest): \UniOne\Model\WebhookSet200Response
```

Sets or edits a [webhook](https://docs.unione.io/en/web-api-ref#webhook), i.e. an event notification handler.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\WebhookApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$webhookSetRequest = new \UniOne\Model\WebhookSetRequest();
$webhookSetRequest
    ->setUrl('https://yourhost.example.com/unione-webhook')
    ->setStatus(null)
    ->setEventFormat(null)
    ->setDeliveryInfo(null)
    ->setSingleEvent(null)
    ->setMaxParallel(null)
    ->setEvents((new \UniOne\Model\WebhookEventsObject());

try {
    $result = $apiInstance->webhookSet($webhookSetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhookApi->webhookSet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **webhookSetRequest** | [**\UniOne\Model\WebhookSetRequest**](../Model/WebhookSetRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\WebhookSet200Response**](../Model/WebhookSet200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
