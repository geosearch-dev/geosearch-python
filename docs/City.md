# City


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional] 
**geoname_id** | **int** |  | [optional] 
**name** | **str** |  | [optional] 
**ascii_name** | **str** |  | [optional] 
**country_code** | **str** |  | [optional] 
**admin1_code** | **str** |  | [optional] 
**admin2_code** | **str** |  | [optional] 
**population** | **int** |  | [optional] 
**elevation** | **int** |  | [optional] 
**timezone** | **str** |  | [optional] 
**latitude** | **float** |  | [optional] 
**longitude** | **float** |  | [optional] 
**country** | [**CountryRef**](CountryRef.md) |  | [optional] 
**region** | [**RegionRef**](RegionRef.md) |  | [optional] 

## Example

```python
from geosearch.models.city import City

# TODO update the JSON string below
json = "{}"
# create an instance of City from a JSON string
city_instance = City.from_json(json)
# print the JSON string representation of the object
print(City.to_json())

# convert the object into a dict
city_dict = city_instance.to_dict()
# create an instance of City from a dict
city_from_dict = City.from_dict(city_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


