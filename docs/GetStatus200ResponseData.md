# GetStatus200ResponseData


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **str** |  | [optional] 
**database** | **str** |  | [optional] 

## Example

```python
from geoapi.models.get_status200_response_data import GetStatus200ResponseData

# TODO update the JSON string below
json = "{}"
# create an instance of GetStatus200ResponseData from a JSON string
get_status200_response_data_instance = GetStatus200ResponseData.from_json(json)
# print the JSON string representation of the object
print(GetStatus200ResponseData.to_json())

# convert the object into a dict
get_status200_response_data_dict = get_status200_response_data_instance.to_dict()
# create an instance of GetStatus200ResponseData from a dict
get_status200_response_data_from_dict = GetStatus200ResponseData.from_dict(get_status200_response_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


