# # EventDumpObject

## Properties

Name | Type | Description | Notes | Example | Required
------------ | ------------- | ------------- | ------------- | ------------- | -------------
**dumpId** | **string** | Dump ID received by the method [event-dump/create](https://docs.unione.io/en/web-api-ref#event-dump-create). | | Gqfasjh34tlasd |  true 
**dumpStatus** | **string** | Task status, possible values are:&lt;br&gt;&lt;br&gt;* __queued__ - the task is in the queue, processing is not started yet;* __in_process__ - the request is being processed;* __ready__ - the task is finished, dump file is ready for download;* __failed__ - processing failed due to an internal error. | | in_process |  true 
**files** | [**\UniOne\Model\EventDumpFilesObject[]**](EventDumpFilesObject.md) | An array of objects, each representing a file, ready for download. You may start downloading everything listed in “files” even if **dump_status** is still **in_process**. If there are no events, according to the specified parameters, an empty array will be returned. | | null | 

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
