# ErrorResponseError


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**code** | **str** |  | 
**message** | **str** |  | 
**details** | [**List[ErrorResponseErrorDetailsInner]**](ErrorResponseErrorDetailsInner.md) |  | [optional] 
**request_id** | **str** | Correlation identifier present on every error response. Quote this when contacting support. | 
**trace_id** | **str** | W3C trace ID of the distributed trace for this request, when tracing is enabled. Omitted entirely when no span was recording, so clients must treat it as optional. It complements rather than replaces &#x60;request_id&#x60;. | [optional] 
**quota** | [**QuotaDetail**](QuotaDetail.md) |  | [optional] 
**upgrade** | [**UpgradeDetail**](UpgradeDetail.md) |  | [optional] 

## Example

```python
from geosearch.models.error_response_error import ErrorResponseError

# TODO update the JSON string below
json = "{}"
# create an instance of ErrorResponseError from a JSON string
error_response_error_instance = ErrorResponseError.from_json(json)
# print the JSON string representation of the object
print(ErrorResponseError.to_json())

# convert the object into a dict
error_response_error_dict = error_response_error_instance.to_dict()
# create an instance of ErrorResponseError from a dict
error_response_error_from_dict = ErrorResponseError.from_dict(error_response_error_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


