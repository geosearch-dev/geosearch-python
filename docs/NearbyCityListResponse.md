# NearbyCityListResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[NearbyCity]**](NearbyCity.md) |  | [optional] 
**meta** | [**PaginationMeta**](PaginationMeta.md) |  | [optional] 

## Example

```python
from geosearch.models.nearby_city_list_response import NearbyCityListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of NearbyCityListResponse from a JSON string
nearby_city_list_response_instance = NearbyCityListResponse.from_json(json)
# print the JSON string representation of the object
print(NearbyCityListResponse.to_json())

# convert the object into a dict
nearby_city_list_response_dict = nearby_city_list_response_instance.to_dict()
# create an instance of NearbyCityListResponse from a dict
nearby_city_list_response_from_dict = NearbyCityListResponse.from_dict(nearby_city_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


