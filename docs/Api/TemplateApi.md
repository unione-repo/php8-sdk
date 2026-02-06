# UniOne\TemplateApi

All URIs are relative to https://api.unione.io/en/transactional/api/v1

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**templateDelete()**](TemplateApi.md#templateDelete) | **POST** /template/delete.json | Deletes a template by id. |
| [**templateGet()**](TemplateApi.md#templateGet) | **POST** /template/get.json | Gets template properties by it&#39;s id. |
| [**templateList()**](TemplateApi.md#templateList) | **POST** /template/list.json | Returns the list of all or some templates of the account. |
| [**templateSet()**](TemplateApi.md#templateSet) | **POST** /template/set.json | Creates or updates an email template. |


## `templateDelete()`

```php
templateDelete($templateGetRequest): \UniOne\Model\SuccessResponse
```

Deletes a template by id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\TemplateApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$templateGetRequest = new \UniOne\Model\TemplateGetRequest();
$templateGetRequest
    ->setId('00000000-0000-0000-0000-000000000000');

try {
    $result = $apiInstance->templateDelete($templateGetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplateApi->templateDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **templateGetRequest** | [**\UniOne\Model\TemplateGetRequest**](../Model/TemplateGetRequest.md)|  | |  true 

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

## `templateGet()`

```php
templateGet($templateGetRequest): \UniOne\Model\TemplateSet200Response
```

Gets template properties by it's id.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\TemplateApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$templateGetRequest = new \UniOne\Model\TemplateGetRequest();
$templateGetRequest
    ->setId('00000000-0000-0000-0000-000000000000');

try {
    $result = $apiInstance->templateGet($templateGetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplateApi->templateGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **templateGetRequest** | [**\UniOne\Model\TemplateGetRequest**](../Model/TemplateGetRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\TemplateSet200Response**](../Model/TemplateSet200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `templateList()`

```php
templateList($templateListRequest): \UniOne\Model\TemplateList200Response
```

Returns the list of all or some templates of the account.

You can iterate thru large list using **offset** and **limit** parameters. When less than **limit** templates are returned then the end of list is reached.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\TemplateApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$templateListRequest = new \UniOne\Model\TemplateListRequest();
$templateListRequest
    ->setLimit(null)
    ->setOffset(null);

try {
    $result = $apiInstance->templateList($templateListRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplateApi->templateList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **templateListRequest** | [**\UniOne\Model\TemplateListRequest**](../Model/TemplateListRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\TemplateList200Response**](../Model/TemplateList200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `templateSet()`

```php
templateSet($templateSetRequest): \UniOne\Model\TemplateSet200Response
```

Creates or updates an email template.

Restrictions:<br>* The maximum request size is 10 MB.<br>* The number of templates is limited to 10000.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\TemplateApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$templateSetRequest = new \UniOne\Model\TemplateSetRequest();
$templateSetRequest
    ->setTemplate((new \UniOne\Model\TemplateObject());

try {
    $result = $apiInstance->templateSet($templateSetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplateApi->templateSet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **templateSetRequest** | [**\UniOne\Model\TemplateSetRequest**](../Model/TemplateSetRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\TemplateSet200Response**](../Model/TemplateSet200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
