# Country


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  | [optional] 
**geoname_id** | **int** |  | [optional] 
**iso_code** | **str** |  | [optional] 
**iso3_code** | **str** |  | [optional] 
**iso_numeric** | **int** |  | [optional] 
**fips_code** | **str** |  | [optional] 
**name** | **str** |  | [optional] 
**capital** | **str** |  | [optional] 
**area_sq_km** | **float** |  | [optional] 
**population** | **int** |  | [optional] 
**continent_code** | **str** |  | [optional] 
**tld** | **str** |  | [optional] 
**currency_code** | **str** |  | [optional] 
**currency_name** | **str** |  | [optional] 
**phone** | **str** |  | [optional] 
**postal_code_format** | **str** |  | [optional] 
**postal_code_regex** | **str** |  | [optional] 
**languages** | **List[str]** |  | [optional] 
**neighbours** | **List[str]** |  | [optional] 
**latitude** | **float** |  | [optional] 
**longitude** | **float** |  | [optional] 
**flag_emoji** | **str** |  | [optional] 
**geometry** | [**GeoJSONMultiPolygon**](GeoJSONMultiPolygon.md) | Country boundary. Returned by default on &#x60;GET /v1/countries/{code}&#x60; and on request via &#x60;?fields&#x3D;geometry&#x60; on &#x60;GET /v1/countries&#x60;.  NOT TIER-GATED. Country geometry is served on every plan, including Free. Region geometry is gated — see the &#x60;Region&#x60; schema. | [optional] 

## Example

```python
from geosearch.models.country import Country

# TODO update the JSON string below
json = "{}"
# create an instance of Country from a JSON string
country_instance = Country.from_json(json)
# print the JSON string representation of the object
print(Country.to_json())

# convert the object into a dict
country_dict = country_instance.to_dict()
# create an instance of Country from a dict
country_from_dict = Country.from_dict(country_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


