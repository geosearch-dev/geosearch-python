# ReverseGeocodeResult


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**city** | [**NearbyCity**](NearbyCity.md) |  | [optional] 
**distance_km** | **float** |  | [optional] 

## Example

```python
from geoapi.models.reverse_geocode_result import ReverseGeocodeResult

# TODO update the JSON string below
json = "{}"
# create an instance of ReverseGeocodeResult from a JSON string
reverse_geocode_result_instance = ReverseGeocodeResult.from_json(json)
# print the JSON string representation of the object
print(ReverseGeocodeResult.to_json())

# convert the object into a dict
reverse_geocode_result_dict = reverse_geocode_result_instance.to_dict()
# create an instance of ReverseGeocodeResult from a dict
reverse_geocode_result_from_dict = ReverseGeocodeResult.from_dict(reverse_geocode_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


