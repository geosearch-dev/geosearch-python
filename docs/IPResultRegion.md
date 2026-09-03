# IPResultRegion


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**iso_code** | **str** |  | [optional] 
**name** | **str** |  | [optional] 

## Example

```python
from geosearch.models.ip_result_region import IPResultRegion

# TODO update the JSON string below
json = "{}"
# create an instance of IPResultRegion from a JSON string
ip_result_region_instance = IPResultRegion.from_json(json)
# print the JSON string representation of the object
print(IPResultRegion.to_json())

# convert the object into a dict
ip_result_region_dict = ip_result_region_instance.to_dict()
# create an instance of IPResultRegion from a dict
ip_result_region_from_dict = IPResultRegion.from_dict(ip_result_region_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


