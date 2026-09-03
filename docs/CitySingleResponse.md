# CitySingleResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**City**](City.md) |  | [optional] 

## Example

```python
from geosearch.models.city_single_response import CitySingleResponse

# TODO update the JSON string below
json = "{}"
# create an instance of CitySingleResponse from a JSON string
city_single_response_instance = CitySingleResponse.from_json(json)
# print the JSON string representation of the object
print(CitySingleResponse.to_json())

# convert the object into a dict
city_single_response_dict = city_single_response_instance.to_dict()
# create an instance of CitySingleResponse from a dict
city_single_response_from_dict = CitySingleResponse.from_dict(city_single_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


