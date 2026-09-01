# GeoJSONGeometry

A bare GeoJSON geometry — the `{\"type\": ..., \"coordinates\": ...}` object itself, NOT a GeoJSON `Feature`. There is no `properties` wrapper.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** | &#x60;MultiPolygon&#x60; for most areas, &#x60;Polygon&#x60; for areas with a single ring — including areas that BECOME single-ring under &#x60;?simplify&#x3D;&#x60;. Do not pin this to one value. | 
**coordinates** | **List[object]** | Nesting depth depends on &#x60;type&#x60;: three levels for &#x60;Polygon&#x60;, four for &#x60;MultiPolygon&#x60;. Positions are &#x60;[longitude, latitude]&#x60; in EPSG:4326, per the GeoJSON specification. | 

## Example

```python
from geoapi.models.geo_json_geometry import GeoJSONGeometry

# TODO update the JSON string below
json = "{}"
# create an instance of GeoJSONGeometry from a JSON string
geo_json_geometry_instance = GeoJSONGeometry.from_json(json)
# print the JSON string representation of the object
print(GeoJSONGeometry.to_json())

# convert the object into a dict
geo_json_geometry_dict = geo_json_geometry_instance.to_dict()
# create an instance of GeoJSONGeometry from a dict
geo_json_geometry_from_dict = GeoJSONGeometry.from_dict(geo_json_geometry_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


