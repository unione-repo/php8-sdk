# UniOne\SuppressionApi

All URIs are relative to https://api.unione.io/en/transactional/api/v1

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**suppressionDelete()**](SuppressionApi.md#suppressionDelete) | **POST** /suppression/delete.json | Deletes an email from suppression list (only records with is_deletable&#x3D;true). If there are no entries of this email in the suppression list, API error 3003 is returned. If such entries exist but no one can be deleted, API error 3004 is returned. If daily limit of deletes exceeded, API error 906 is returned. |
| [**suppressionGet()**](SuppressionApi.md#suppressionGet) | **POST** /suppression/get.json | Gets a reason and date of email suppression. |
| [**suppressionList()**](SuppressionApi.md#suppressionList) | **POST** /suppression/list.json | Returns a suppression list since provided date. |
| [**suppressionSet()**](SuppressionApi.md#suppressionSet) | **POST** /suppression/set.json | Adds an email address to the suppression list. You can always remove this address from the suppression list later using the [suppression/delete](https://docs.unione.io/en/web-api-ref#suppression-delete) method. |


## `suppressionDelete()`

```php
suppressionDelete($suppressionDeleteRequest): \UniOne\Model\SuccessResponse
```

Deletes an email from suppression list (only records with is_deletable=true). If there are no entries of this email in the suppression list, API error 3003 is returned. If such entries exist but no one can be deleted, API error 3004 is returned. If daily limit of deletes exceeded, API error 906 is returned.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\SuppressionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$suppressionDeleteRequest = new \UniOne\Model\SuppressionDeleteRequest();
$suppressionDeleteRequest
    ->setEmail('email@example.com');

try {
    $result = $apiInstance->suppressionDelete($suppressionDeleteRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SuppressionApi->suppressionDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **suppressionDeleteRequest** | [**\UniOne\Model\SuppressionDeleteRequest**](../Model/SuppressionDeleteRequest.md)|  | |  true 

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

## `suppressionGet()`

```php
suppressionGet($suppressionGetRequest): \UniOne\Model\SuppressionGet200Response
```

Gets a reason and date of email suppression.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\SuppressionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$suppressionGetRequest = new \UniOne\Model\SuppressionGetRequest();
$suppressionGetRequest
    ->setEmail('email@example.com')
    ->setAllProjects(null);

try {
    $result = $apiInstance->suppressionGet($suppressionGetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SuppressionApi->suppressionGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **suppressionGetRequest** | [**\UniOne\Model\SuppressionGetRequest**](../Model/SuppressionGetRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\SuppressionGet200Response**](../Model/SuppressionGet200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `suppressionList()`

```php
suppressionList($suppressionListRequest): \UniOne\Model\SuppressionList200Response
```

Returns a suppression list since provided date.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\SuppressionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$suppressionListRequest = new \UniOne\Model\SuppressionListRequest();
$suppressionListRequest
    ->setCause('unsubscribed')
    ->setSource('user')
    ->setStartTime('2020-10-14 17:00:00')
    ->setCursor('Ajfb6Hvdkn3hdhhvG57xbdufhG5')
    ->setLimit(50);

try {
    $result = $apiInstance->suppressionList($suppressionListRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SuppressionApi->suppressionList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **suppressionListRequest** | [**\UniOne\Model\SuppressionListRequest**](../Model/SuppressionListRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\SuppressionList200Response**](../Model/SuppressionList200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `suppressionSet()`

```php
suppressionSet($suppressionSetRequest): \UniOne\Model\SuccessResponse
```

Adds an email address to the suppression list. You can always remove this address from the suppression list later using the [suppression/delete](https://docs.unione.io/en/web-api-ref#suppression-delete) method.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\SuppressionApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$suppressionSetRequest = new \UniOne\Model\SuppressionSetRequest();
$suppressionSetRequest
    ->setEmail('email@example.com')
    ->setCause('unsubscribed')
    ->setCreated('2021-12-19 10:15:49');

try {
    $result = $apiInstance->suppressionSet($suppressionSetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SuppressionApi->suppressionSet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **suppressionSetRequest** | [**\UniOne\Model\SuppressionSetRequest**](../Model/SuppressionSetRequest.md)|  | |  true 

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
