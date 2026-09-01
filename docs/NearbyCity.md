# NearbyCity


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional] 
**name** | **str** |  | [optional] 
**country_code** | **str** |  | [optional] 
**population** | **int** |  | [optional] 
**timezone** | **str** |  | [optional] 
**latitude** | **float** |  | [optional] 
**longitude** | **float** |  | [optional] 
**distance_km** | **float** |  | [optional] 
**country** | [**CountryRef**](CountryRef.md) |  | [optional] 
**region** | [**RegionRef**](RegionRef.md) |  | [optional] 

## Example

```python
from geoapi.models.nearby_city import NearbyCity

# TODO update the JSON string below
json = "{}"
# create an instance of NearbyCity from a JSON string
nearby_city_instance = NearbyCity.from_json(json)
# print the JSON string representation of the object
print(NearbyCity.to_json())

# convert the object into a dict
nearby_city_dict = nearby_city_instance.to_dict()
# create an instance of NearbyCity from a dict
nearby_city_from_dict = NearbyCity.from_dict(nearby_city_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


