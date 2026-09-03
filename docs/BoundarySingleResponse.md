# BoundarySingleResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**Boundary**](Boundary.md) |  | [optional] 

## Example

```python
from geosearch.models.boundary_single_response import BoundarySingleResponse

# TODO update the JSON string below
json = "{}"
# create an instance of BoundarySingleResponse from a JSON string
boundary_single_response_instance = BoundarySingleResponse.from_json(json)
# print the JSON string representation of the object
print(BoundarySingleResponse.to_json())

# convert the object into a dict
boundary_single_response_dict = boundary_single_response_instance.to_dict()
# create an instance of BoundarySingleResponse from a dict
boundary_single_response_from_dict = BoundarySingleResponse.from_dict(boundary_single_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


