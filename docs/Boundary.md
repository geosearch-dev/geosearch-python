# Boundary

One area's boundary polygon, as returned by `GET /v1/boundaries/{geoname_id}`.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**geoname_id** | **int** | The area the polygon belongs to, read back from the source row rather than echoed from the request. | 
**name** | **str** | The area&#39;s name, resolved through &#x60;?lang&#x3D;&#x60; when supplied. | 
**type** | **str** | Which kind of area this is. | 
**geometry** | [**GeoJSONGeometry**](GeoJSONGeometry.md) |  | 
**simplify** | **float** | The tolerance that was ACTUALLY APPLIED, or &#x60;null&#x60; for full precision.  THIS IS NOT YOUR &#x60;?simplify&#x3D;&#x60; ECHOED BACK. A requested tolerance of &#x60;0&#x60; is dropped rather than executed, so &#x60;?simplify&#x3D;0&#x60; returns &#x60;null&#x60; here — that is the truthful answer, because no simplification was performed. Read this field rather than assuming the request was honoured verbatim. | 

## Example

```python
from geoapi.models.boundary import Boundary

# TODO update the JSON string below
json = "{}"
# create an instance of Boundary from a JSON string
boundary_instance = Boundary.from_json(json)
# print the JSON string representation of the object
print(Boundary.to_json())

# convert the object into a dict
boundary_dict = boundary_instance.to_dict()
# create an instance of Boundary from a dict
boundary_from_dict = Boundary.from_dict(boundary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


