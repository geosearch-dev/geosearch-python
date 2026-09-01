# UpgradeDetail

Structured detail accompanying a `tier_upgrade_required` 403. Present only on that response; absent from every other error body.  ONE FIELD, DELIBERATELY. It says where to go and claims nothing else. It carries no limit, no usage and no reset instant, because none of those describe a plan that simply does not include the feature — there is no quantity to wait for and nothing resets.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**upgrade_url** | **str** | Absolute URL of the billing page where the plan can be raised. Derived server-side from configuration and never reflected from a request header or parameter. | 

## Example

```python
from geoapi.models.upgrade_detail import UpgradeDetail

# TODO update the JSON string below
json = "{}"
# create an instance of UpgradeDetail from a JSON string
upgrade_detail_instance = UpgradeDetail.from_json(json)
# print the JSON string representation of the object
print(UpgradeDetail.to_json())

# convert the object into a dict
upgrade_detail_dict = upgrade_detail_instance.to_dict()
# create an instance of UpgradeDetail from a dict
upgrade_detail_from_dict = UpgradeDetail.from_dict(upgrade_detail_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


