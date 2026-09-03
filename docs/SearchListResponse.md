# SearchListResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[SearchResult]**](SearchResult.md) |  | [optional] 
**meta** | [**PaginationMeta**](PaginationMeta.md) |  | [optional] 

## Example

```python
from geosearch.models.search_list_response import SearchListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of SearchListResponse from a JSON string
search_list_response_instance = SearchListResponse.from_json(json)
# print the JSON string representation of the object
print(SearchListResponse.to_json())

# convert the object into a dict
search_list_response_dict = search_list_response_instance.to_dict()
# create an instance of SearchListResponse from a dict
search_list_response_from_dict = SearchListResponse.from_dict(search_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


