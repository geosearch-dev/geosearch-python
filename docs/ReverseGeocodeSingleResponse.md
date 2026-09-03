# ReverseGeocodeSingleResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**ReverseGeocodeResult**](ReverseGeocodeResult.md) |  | [optional] 

## Example

```python
from geosearch.models.reverse_geocode_single_response import ReverseGeocodeSingleResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ReverseGeocodeSingleResponse from a JSON string
reverse_geocode_single_response_instance = ReverseGeocodeSingleResponse.from_json(json)
# print the JSON string representation of the object
print(ReverseGeocodeSingleResponse.to_json())

# convert the object into a dict
reverse_geocode_single_response_dict = reverse_geocode_single_response_instance.to_dict()
# create an instance of ReverseGeocodeSingleResponse from a dict
reverse_geocode_single_response_from_dict = ReverseGeocodeSingleResponse.from_dict(reverse_geocode_single_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


