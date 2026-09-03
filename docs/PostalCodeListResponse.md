# PostalCodeListResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[PostalCode]**](PostalCode.md) |  | [optional] 
**meta** | [**PaginationMeta**](PaginationMeta.md) |  | [optional] 

## Example

```python
from geosearch.models.postal_code_list_response import PostalCodeListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of PostalCodeListResponse from a JSON string
postal_code_list_response_instance = PostalCodeListResponse.from_json(json)
# print the JSON string representation of the object
print(PostalCodeListResponse.to_json())

# convert the object into a dict
postal_code_list_response_dict = postal_code_list_response_instance.to_dict()
# create an instance of PostalCodeListResponse from a dict
postal_code_list_response_from_dict = PostalCodeListResponse.from_dict(postal_code_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


