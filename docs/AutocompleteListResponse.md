# AutocompleteListResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[AutocompleteResult]**](AutocompleteResult.md) |  | [optional] 
**meta** | [**PaginationMeta**](PaginationMeta.md) |  | [optional] 

## Example

```python
from geosearch.models.autocomplete_list_response import AutocompleteListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of AutocompleteListResponse from a JSON string
autocomplete_list_response_instance = AutocompleteListResponse.from_json(json)
# print the JSON string representation of the object
print(AutocompleteListResponse.to_json())

# convert the object into a dict
autocomplete_list_response_dict = autocomplete_list_response_instance.to_dict()
# create an instance of AutocompleteListResponse from a dict
autocomplete_list_response_from_dict = AutocompleteListResponse.from_dict(autocomplete_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


