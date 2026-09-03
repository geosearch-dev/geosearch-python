# CityListResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[City]**](City.md) |  | [optional] 
**meta** | [**PaginationMeta**](PaginationMeta.md) |  | [optional] 

## Example

```python
from geosearch.models.city_list_response import CityListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of CityListResponse from a JSON string
city_list_response_instance = CityListResponse.from_json(json)
# print the JSON string representation of the object
print(CityListResponse.to_json())

# convert the object into a dict
city_list_response_dict = city_list_response_instance.to_dict()
# create an instance of CityListResponse from a dict
city_list_response_from_dict = CityListResponse.from_dict(city_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


