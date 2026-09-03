# CountryRef


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**iso_code** | **str** |  | [optional] 
**name** | **str** |  | [optional] 

## Example

```python
from geosearch.models.country_ref import CountryRef

# TODO update the JSON string below
json = "{}"
# create an instance of CountryRef from a JSON string
country_ref_instance = CountryRef.from_json(json)
# print the JSON string representation of the object
print(CountryRef.to_json())

# convert the object into a dict
country_ref_dict = country_ref_instance.to_dict()
# create an instance of CountryRef from a dict
country_ref_from_dict = CountryRef.from_dict(country_ref_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


