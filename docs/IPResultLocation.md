# IPResultLocation


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**latitude** | **float** |  | [optional] 
**longitude** | **float** |  | [optional] 
**accuracy_radius** | **int** |  | [optional] 
**timezone** | **str** |  | [optional] 

## Example

```python
from geoapi.models.ip_result_location import IPResultLocation

# TODO update the JSON string below
json = "{}"
# create an instance of IPResultLocation from a JSON string
ip_result_location_instance = IPResultLocation.from_json(json)
# print the JSON string representation of the object
print(IPResultLocation.to_json())

# convert the object into a dict
ip_result_location_dict = ip_result_location_instance.to_dict()
# create an instance of IPResultLocation from a dict
ip_result_location_from_dict = IPResultLocation.from_dict(ip_result_location_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


