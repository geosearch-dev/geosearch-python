# HierarchyListResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[HierarchyNode]**](HierarchyNode.md) |  | [optional] 
**meta** | [**PaginationMeta**](PaginationMeta.md) |  | [optional] 

## Example

```python
from geoapi.models.hierarchy_list_response import HierarchyListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of HierarchyListResponse from a JSON string
hierarchy_list_response_instance = HierarchyListResponse.from_json(json)
# print the JSON string representation of the object
print(HierarchyListResponse.to_json())

# convert the object into a dict
hierarchy_list_response_dict = hierarchy_list_response_instance.to_dict()
# create an instance of HierarchyListResponse from a dict
hierarchy_list_response_from_dict = HierarchyListResponse.from_dict(hierarchy_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


