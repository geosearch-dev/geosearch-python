# PostalCode


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional] 
**country_code** | **str** |  | [optional] 
**postal_code** | **str** |  | [optional] 
**place_name** | **str** |  | [optional] 
**admin_name1** | **str** |  | [optional] 
**admin_code1** | **str** |  | [optional] 
**admin_name2** | **str** |  | [optional] 
**admin_code2** | **str** |  | [optional] 
**admin_name3** | **str** |  | [optional] 
**admin_code3** | **str** |  | [optional] 
**latitude** | **float** |  | [optional] 
**longitude** | **float** |  | [optional] 
**accuracy** | **int** |  | [optional] 
**country** | [**CountryRef**](CountryRef.md) |  | [optional] 

## Example

```python
from geoapi.models.postal_code import PostalCode

# TODO update the JSON string below
json = "{}"
# create an instance of PostalCode from a JSON string
postal_code_instance = PostalCode.from_json(json)
# print the JSON string representation of the object
print(PostalCode.to_json())

# convert the object into a dict
postal_code_dict = postal_code_instance.to_dict()
# create an instance of PostalCode from a dict
postal_code_from_dict = PostalCode.from_dict(postal_code_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


