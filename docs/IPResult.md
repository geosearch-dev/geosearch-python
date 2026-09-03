# IPResult


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ip** | **str** |  | [optional] 
**network** | **str** |  | [optional] 
**continent** | [**IPResultContinent**](IPResultContinent.md) |  | [optional] 
**country** | [**IPResultCountry**](IPResultCountry.md) |  | [optional] 
**region** | [**IPResultRegion**](IPResultRegion.md) |  | [optional] 
**city** | [**IPResultCity**](IPResultCity.md) |  | [optional] 
**postal** | [**IPResultPostal**](IPResultPostal.md) |  | [optional] 
**location** | [**IPResultLocation**](IPResultLocation.md) |  | [optional] 
**is_anonymous_proxy** | **bool** |  | [optional] 
**is_satellite_provider** | **bool** |  | [optional] 

## Example

```python
from geosearch.models.ip_result import IPResult

# TODO update the JSON string below
json = "{}"
# create an instance of IPResult from a JSON string
ip_result_instance = IPResult.from_json(json)
# print the JSON string representation of the object
print(IPResult.to_json())

# convert the object into a dict
ip_result_dict = ip_result_instance.to_dict()
# create an instance of IPResult from a dict
ip_result_from_dict = IPResult.from_dict(ip_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


