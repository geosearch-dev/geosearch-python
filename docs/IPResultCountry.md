# IPResultCountry


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**iso_code** | **str** |  | [optional] 
**name** | **str** |  | [optional] 
**is_in_european_union** | **bool** |  | [optional] 

## Example

```python
from geosearch.models.ip_result_country import IPResultCountry

# TODO update the JSON string below
json = "{}"
# create an instance of IPResultCountry from a JSON string
ip_result_country_instance = IPResultCountry.from_json(json)
# print the JSON string representation of the object
print(IPResultCountry.to_json())

# convert the object into a dict
ip_result_country_dict = ip_result_country_instance.to_dict()
# create an instance of IPResultCountry from a dict
ip_result_country_from_dict = IPResultCountry.from_dict(ip_result_country_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


