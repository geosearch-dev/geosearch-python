# RegionRef


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional] 
**name** | **str** |  | [optional] 
**admin_code** | **str** |  | [optional] 

## Example

```python
from geosearch.models.region_ref import RegionRef

# TODO update the JSON string below
json = "{}"
# create an instance of RegionRef from a JSON string
region_ref_instance = RegionRef.from_json(json)
# print the JSON string representation of the object
print(RegionRef.to_json())

# convert the object into a dict
region_ref_dict = region_ref_instance.to_dict()
# create an instance of RegionRef from a dict
region_ref_from_dict = RegionRef.from_dict(region_ref_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


