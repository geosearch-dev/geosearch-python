# RegionSingleResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**Region**](Region.md) |  | [optional] 

## Example

```python
from geosearch.models.region_single_response import RegionSingleResponse

# TODO update the JSON string below
json = "{}"
# create an instance of RegionSingleResponse from a JSON string
region_single_response_instance = RegionSingleResponse.from_json(json)
# print the JSON string representation of the object
print(RegionSingleResponse.to_json())

# convert the object into a dict
region_single_response_dict = region_single_response_instance.to_dict()
# create an instance of RegionSingleResponse from a dict
region_single_response_from_dict = RegionSingleResponse.from_dict(region_single_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


