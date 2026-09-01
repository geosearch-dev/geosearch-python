# TimezoneSingleResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**Timezone**](Timezone.md) |  | [optional] 

## Example

```python
from geoapi.models.timezone_single_response import TimezoneSingleResponse

# TODO update the JSON string below
json = "{}"
# create an instance of TimezoneSingleResponse from a JSON string
timezone_single_response_instance = TimezoneSingleResponse.from_json(json)
# print the JSON string representation of the object
print(TimezoneSingleResponse.to_json())

# convert the object into a dict
timezone_single_response_dict = timezone_single_response_instance.to_dict()
# create an instance of TimezoneSingleResponse from a dict
timezone_single_response_from_dict = TimezoneSingleResponse.from_dict(timezone_single_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


