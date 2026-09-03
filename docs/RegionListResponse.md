# RegionListResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[Region]**](Region.md) |  | [optional] 
**meta** | [**PaginationMeta**](PaginationMeta.md) |  | [optional] 

## Example

```python
from geosearch.models.region_list_response import RegionListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of RegionListResponse from a JSON string
region_list_response_instance = RegionListResponse.from_json(json)
# print the JSON string representation of the object
print(RegionListResponse.to_json())

# convert the object into a dict
region_list_response_dict = region_list_response_instance.to_dict()
# create an instance of RegionListResponse from a dict
region_list_response_from_dict = RegionListResponse.from_dict(region_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


