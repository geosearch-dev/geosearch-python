# CountryListResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[Country]**](Country.md) |  | [optional] 
**meta** | [**PaginationMeta**](PaginationMeta.md) |  | [optional] 

## Example

```python
from geoapi.models.country_list_response import CountryListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of CountryListResponse from a JSON string
country_list_response_instance = CountryListResponse.from_json(json)
# print the JSON string representation of the object
print(CountryListResponse.to_json())

# convert the object into a dict
country_list_response_dict = country_list_response_instance.to_dict()
# create an instance of CountryListResponse from a dict
country_list_response_from_dict = CountryListResponse.from_dict(country_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


