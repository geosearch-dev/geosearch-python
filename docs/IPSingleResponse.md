# IPSingleResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**IPResult**](IPResult.md) |  | [optional] 

## Example

```python
from geoapi.models.ip_single_response import IPSingleResponse

# TODO update the JSON string below
json = "{}"
# create an instance of IPSingleResponse from a JSON string
ip_single_response_instance = IPSingleResponse.from_json(json)
# print the JSON string representation of the object
print(IPSingleResponse.to_json())

# convert the object into a dict
ip_single_response_dict = ip_single_response_instance.to_dict()
# create an instance of IPSingleResponse from a dict
ip_single_response_from_dict = IPSingleResponse.from_dict(ip_single_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


