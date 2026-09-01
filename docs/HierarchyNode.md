# HierarchyNode


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**geoname_id** | **int** |  | [optional] 
**name** | **str** |  | [optional] 
**type** | **str** |  | [optional] 
**depth** | **int** | THE DIRECTION DEPENDS ON THE ENDPOINT, because this schema is shared by two operations that number their nodes from opposite ends.  On &#x60;GET /v1/cities/{id}/hierarchy&#x60; depth counts UP from the entity asked about: &#x60;depth: 0&#x60; is the city and the country carries the HIGHEST depth. On &#x60;GET /v1/resolve&#x60; depth is POSITIONAL, counting outward-in: &#x60;depth: 0&#x60; is the COUNTRY. Code that sorts or indexes on this field across both endpoints without accounting for the inversion silently REVERSES the hierarchy rather than failing — &#x60;max(by: depth)&#x60; returns the country on one and the innermost region on the other.  On &#x60;/v1/resolve&#x60; depth is the ARRAY INDEX and NOT an administrative level. A chain may skip a level: a measured 3.8% of coordinates resolve to a country plus a level-2 region with no level-1 region, and in those &#x60;depth: 1&#x60; is a level-2 area. &#x60;HierarchyNode&#x60; carries no &#x60;level&#x60; field, so there is no second signal to disambiguate with — treat depth as position only. | [optional] 

## Example

```python
from geoapi.models.hierarchy_node import HierarchyNode

# TODO update the JSON string below
json = "{}"
# create an instance of HierarchyNode from a JSON string
hierarchy_node_instance = HierarchyNode.from_json(json)
# print the JSON string representation of the object
print(HierarchyNode.to_json())

# convert the object into a dict
hierarchy_node_dict = hierarchy_node_instance.to_dict()
# create an instance of HierarchyNode from a dict
hierarchy_node_from_dict = HierarchyNode.from_dict(hierarchy_node_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


