# UniOne\EventDumpApi

All URIs are relative to https://api.unione.io/en/transactional/api/v1

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**eventDumpCreate()**](EventDumpApi.md#eventDumpCreate) | **POST** /event-dump/create.json | This asynchronous method initiates the preparation of data dump in CSV format. The number of dump files created or stored is limited to 10; to order more files, you have to delete one of the previous ones or wait until they will be deleted automatically. A newly created dump file is kept for 8 hours. If the request period is more than a day or there are too many events then several files will be generated and each file will contain no more than 100,000 events. File contains columns with the following information - &#39;event_time&#39;, &#39;job_id&#39;, &#39;from_email&#39;, &#39;email&#39;, &#39;status&#39;, &#39;delivery_status&#39;, &#39;metadata&#39;, &#39;destination_response&#39;, &#39;user_agent&#39;, &#39;url&#39;, &#39;ip&#39;, &#39;tags&#39; and &#39;project_id&#39; (for accounts with projects enabled). You can change the fields and include &#39;subject&#39; field using &#39;dump_fileds&#39; parameter. |
| [**eventDumpDelete()**](EventDumpApi.md#eventDumpDelete) | **POST** /event-dump/delete.json | Removes dump from queue or storage. |
| [**eventDumpGet()**](EventDumpApi.md#eventDumpGet) | **POST** /event-dump/get.json | Returns dump properties for a given identifier |
| [**eventDumpList()**](EventDumpApi.md#eventDumpList) | **POST** /event-dump/list.json | This method does not require any parameters; returns the full list of existing dumps. |


## `eventDumpCreate()`

```php
eventDumpCreate($eventDumpCreateRequest): \UniOne\Model\EventDumpCreate200Response
```

This asynchronous method initiates the preparation of data dump in CSV format. The number of dump files created or stored is limited to 10; to order more files, you have to delete one of the previous ones or wait until they will be deleted automatically. A newly created dump file is kept for 8 hours. If the request period is more than a day or there are too many events then several files will be generated and each file will contain no more than 100,000 events. File contains columns with the following information - 'event_time', 'job_id', 'from_email', 'email', 'status', 'delivery_status', 'metadata', 'destination_response', 'user_agent', 'url', 'ip', 'tags' and 'project_id' (for accounts with projects enabled). You can change the fields and include 'subject' field using 'dump_fileds' parameter.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\EventDumpApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$eventDumpCreateRequest = new \UniOne\Model\EventDumpCreateRequest();
$eventDumpCreateRequest
    ->setStartTime('2022-07-20 00:00:00')
    ->setEndTime('2022-07-21 00:00:00')
    ->setLimit(50)
    ->setAllProjects(null)
    ->setFilter((new \UniOne\Model\FilterObject())
    ->setDumpFields(["string1"])
    ->setAggregate('day_status')
    ->setDelimiter(';')
    ->setFormat('csv');

try {
    $result = $apiInstance->eventDumpCreate($eventDumpCreateRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EventDumpApi->eventDumpCreate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **eventDumpCreateRequest** | [**\UniOne\Model\EventDumpCreateRequest**](../Model/EventDumpCreateRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\EventDumpCreate200Response**](../Model/EventDumpCreate200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `eventDumpDelete()`

```php
eventDumpDelete($eventDumpDeleteRequest): \UniOne\Model\SuccessResponse
```

Removes dump from queue or storage.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\EventDumpApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$eventDumpDeleteRequest = new \UniOne\Model\EventDumpDeleteRequest();
$eventDumpDeleteRequest
    ->setDumpId('Gqfasjh34tlasd');

try {
    $result = $apiInstance->eventDumpDelete($eventDumpDeleteRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EventDumpApi->eventDumpDelete: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **eventDumpDeleteRequest** | [**\UniOne\Model\EventDumpDeleteRequest**](../Model/EventDumpDeleteRequest.md)|  | |  true 

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

## `eventDumpGet()`

```php
eventDumpGet($eventDumpGetRequest): \UniOne\Model\EventDumpGet200Response
```

Returns dump properties for a given identifier

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\EventDumpApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$eventDumpGetRequest = new \UniOne\Model\EventDumpGetRequest();
$eventDumpGetRequest
    ->setDumpId('Gqfasjh34tlasd');

try {
    $result = $apiInstance->eventDumpGet($eventDumpGetRequest);

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EventDumpApi->eventDumpGet: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description | Notes | Required
| ------------- | ------------- | ------------- | ------------- | ------------- |
| **eventDumpGetRequest** | [**\UniOne\Model\EventDumpGetRequest**](../Model/EventDumpGetRequest.md)|  | |  true 

### Return type

[**\UniOne\Model\EventDumpGet200Response**](../Model/EventDumpGet200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `eventDumpList()`

```php
eventDumpList(): \UniOne\Model\EventDumpList200Response
```

This method does not require any parameters; returns the full list of existing dumps.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: apiKeyAuth
$config = UniOne\Configuration::getDefaultConfiguration()->setApiKey('X-API-KEY', 'YOUR_API_KEY');
$config->setHost('api.unione.io');


$apiInstance = new UniOne\Api\EventDumpApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);


try {
    $result = $apiInstance->eventDumpList();

    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EventDumpApi->eventDumpList: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\UniOne\Model\EventDumpList200Response**](../Model/EventDumpList200Response.md)

### Authorization

[apiKeyAuth](../../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
