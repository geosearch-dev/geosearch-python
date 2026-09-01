# QuotaDetail

Structured detail accompanying a `quota_exceeded` 429. Present only on that response; absent from every other error body. It answers, in machine-readable form, what the limit is, how much was used, when it resets, and where to raise it — the same four facts `error.message` repeats in prose for the benefit of log lines and stack traces.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**limit** | **int** | Monthly request allowance for the account&#39;s current plan. | 
**used** | **int** | Requests consumed in the current quota period. | 
**resets_at** | **datetime** | Start of the next quota period, when &#x60;used&#x60; returns to zero. Matches the &#x60;X-RateLimit-Reset&#x60; header on the same response, expressed as RFC 3339 rather than an epoch second. | 
**upgrade_url** | **str** | Absolute URL of the billing page where the plan can be raised. Derived server-side from configuration and never reflected from a request header or parameter. | 

## Example

```python
from geoapi.models.quota_detail import QuotaDetail

# TODO update the JSON string below
json = "{}"
# create an instance of QuotaDetail from a JSON string
quota_detail_instance = QuotaDetail.from_json(json)
# print the JSON string representation of the object
print(QuotaDetail.to_json())

# convert the object into a dict
quota_detail_dict = quota_detail_instance.to_dict()
# create an instance of QuotaDetail from a dict
quota_detail_from_dict = QuotaDetail.from_dict(quota_detail_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


