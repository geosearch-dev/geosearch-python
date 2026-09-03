# CountrySingleResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**Country**](Country.md) |  | [optional] 

## Example

```python
from geosearch.models.country_single_response import CountrySingleResponse

# TODO update the JSON string below
json = "{}"
# create an instance of CountrySingleResponse from a JSON string
country_single_response_instance = CountrySingleResponse.from_json(json)
# print the JSON string representation of the object
print(CountrySingleResponse.to_json())

# convert the object into a dict
country_single_response_dict = country_single_response_instance.to_dict()
# create an instance of CountrySingleResponse from a dict
country_single_response_from_dict = CountrySingleResponse.from_dict(country_single_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


