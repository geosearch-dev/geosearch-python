# geoapi.PostalCodesApi

All URIs are relative to *https://geosearch.dev*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_postal_codes**](PostalCodesApi.md#list_postal_codes) | **GET** /v1/postal-codes | List postal codes
[**nearest_postal_code**](PostalCodesApi.md#nearest_postal_code) | **GET** /v1/postal-codes/nearest | Find nearest postal codes


# **list_postal_codes**
> PostalCodeListResponse list_postal_codes(lang=lang, country=country, code=code, within=within, bbox=bbox, cursor=cursor, limit=limit, fields=fields, sort=sort)

List postal codes

Returns a paginated list of postal codes with optional filtering by country and code.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.postal_code_list_response import PostalCodeListResponse
from geoapi.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://geosearch.dev
# See configuration.py for a list of all supported configuration parameters.
configuration = geoapi.Configuration(
    host = "https://geosearch.dev"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: apiKeyAuth
configuration.api_key['apiKeyAuth'] = os.environ["API_KEY"]

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['apiKeyAuth'] = 'Bearer'

# Enter a context with an instance of the API client
with geoapi.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = geoapi.PostalCodesApi(api_client)
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    country = 'US' # str | Filter by ISO alpha-2 country codes (comma-separated) (optional)
    code = '94105' # str | Filter by postal code (optional)
    within = 6252001 # int | Return only results whose coordinates fall geometrically inside the boundary of the given area, identified by its GeoNames id. Countries and administrative regions are valid areas; a city id is not.  Accepts exactly one id. A COMMA-SEPARATED LIST IS REJECTED with a 422 naming the limit — a deliberate departure from the comma-separated convention `country` uses, because each value would be a separate polygon intersection. Ask for one area per request.  COST: a request using this parameter consumes 2 quota units instead of 1, on every plan including Free. Combining it with `bbox` still costs 2, not 3 — the highest multiplier applies rather than the sum, and adding a box makes the query cheaper to serve, so it is never penalised.  This asks a GEOMETRIC question and can therefore return a different set of cities than `/v1/regions/{id}/cities`, which asks an administrative one. See that endpoint's description for when and why the two disagree.  Two failures are reported with distinct 400 codes so a typo is distinguishable from a coverage gap: `area_not_an_area` means the id does not name a country or region at all, and `area_no_boundary` means it does but no boundary polygon is available for it yet. (optional)
    bbox = '-122.6,37.6,-122.2,37.9' # str | Return only results inside the bounding box, given as four comma-separated numbers in the order `w,s,e,n` — west longitude, south latitude, east longitude, north latitude.  Longitudes must be within [-180, 180] and latitudes within [-90, 90].  A box where WEST IS GREATER THAN EAST wraps the antimeridian and is fully supported: `bbox=170,-20,-170,-10` is a box around Fiji, evaluated as the union of the two halves it spans. Latitude has no equivalent wrap-around meaning, so `s` greater than `n` is a validation error rather than a wrapped box.  Charged at the standard request cost of 1 unit. Adding it to a `within` query narrows the candidate set before the polygon test and does not raise the charge. (optional)
    cursor = 'eyJpZCI6MjV9' # str | Pagination cursor from a previous response (optional)
    limit = 25 # int | Number of results per page (1-100, default 25) (optional) (default to 25)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)
    sort = 'postal_code' # str | Sort field. Allowed: postal_code, country_code, place_name, id. (optional)

    try:
        # List postal codes
        api_response = api_instance.list_postal_codes(lang=lang, country=country, code=code, within=within, bbox=bbox, cursor=cursor, limit=limit, fields=fields, sort=sort)
        print("The response of PostalCodesApi->list_postal_codes:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PostalCodesApi->list_postal_codes: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **country** | **str**| Filter by ISO alpha-2 country codes (comma-separated) | [optional] 
 **code** | **str**| Filter by postal code | [optional] 
 **within** | **int**| Return only results whose coordinates fall geometrically inside the boundary of the given area, identified by its GeoNames id. Countries and administrative regions are valid areas; a city id is not.  Accepts exactly one id. A COMMA-SEPARATED LIST IS REJECTED with a 422 naming the limit — a deliberate departure from the comma-separated convention &#x60;country&#x60; uses, because each value would be a separate polygon intersection. Ask for one area per request.  COST: a request using this parameter consumes 2 quota units instead of 1, on every plan including Free. Combining it with &#x60;bbox&#x60; still costs 2, not 3 — the highest multiplier applies rather than the sum, and adding a box makes the query cheaper to serve, so it is never penalised.  This asks a GEOMETRIC question and can therefore return a different set of cities than &#x60;/v1/regions/{id}/cities&#x60;, which asks an administrative one. See that endpoint&#39;s description for when and why the two disagree.  Two failures are reported with distinct 400 codes so a typo is distinguishable from a coverage gap: &#x60;area_not_an_area&#x60; means the id does not name a country or region at all, and &#x60;area_no_boundary&#x60; means it does but no boundary polygon is available for it yet. | [optional] 
 **bbox** | **str**| Return only results inside the bounding box, given as four comma-separated numbers in the order &#x60;w,s,e,n&#x60; — west longitude, south latitude, east longitude, north latitude.  Longitudes must be within [-180, 180] and latitudes within [-90, 90].  A box where WEST IS GREATER THAN EAST wraps the antimeridian and is fully supported: &#x60;bbox&#x3D;170,-20,-170,-10&#x60; is a box around Fiji, evaluated as the union of the two halves it spans. Latitude has no equivalent wrap-around meaning, so &#x60;s&#x60; greater than &#x60;n&#x60; is a validation error rather than a wrapped box.  Charged at the standard request cost of 1 unit. Adding it to a &#x60;within&#x60; query narrows the candidate set before the polygon test and does not raise the charge. | [optional] 
 **cursor** | **str**| Pagination cursor from a previous response | [optional] 
 **limit** | **int**| Number of results per page (1-100, default 25) | [optional] [default to 25]
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 
 **sort** | **str**| Sort field. Allowed: postal_code, country_code, place_name, id. | [optional] 

### Return type

[**PostalCodeListResponse**](PostalCodeListResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of postal codes |  -  |
**400** | Invalid request. Distinguish the cases by &#x60;error.code&#x60;: &#x60;bad_request&#x60; is a malformed cursor, sort or pagination value; &#x60;area_not_an_area&#x60; means the &#x60;within&#x60; id does not name a country or region; &#x60;area_no_boundary&#x60; means it names a real area for which no boundary polygon is available. The last two are separate codes on purpose — one is a mistake the caller can fix, the other is a limit of our data that they cannot. |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**422** | One or more query parameters were malformed. &#x60;error.details&#x60; names each offending field and what was wrong with it. |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |
**503** | The containment query exceeded the statement timeout that bounds it.  This is a 503 and NOT a 500, deliberately: the server is healthy and the request was valid — this one query against an unusually large or complex boundary simply ran out of its time budget. It is therefore worth retrying, and worth retrying with a narrower query. Adding &#x60;bbox&#x60; or further filters alongside &#x60;within&#x60; reduces the candidate set before the polygon test and is the most effective remedy.  THIS RESPONSE BELONGS TO THE &#x60;within&#x3D;&#x60; ROUTES ONLY. &#x60;GET /v1/resolve&#x60; and &#x60;GET /v1/boundaries/{geoname_id}&#x60; have their own 503 components (&#x60;ResolveQueryTimeout&#x60; and &#x60;BoundaryQueryTimeout&#x60;) because the remedy above is false on both: neither accepts &#x60;bbox&#x60; or &#x60;within&#x60;. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **nearest_postal_code**
> PostalCodeListResponse nearest_postal_code(lat, lon, lang=lang, limit=limit)

Find nearest postal codes

Returns the nearest postal codes to a given latitude/longitude using PostGIS spatial index.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.postal_code_list_response import PostalCodeListResponse
from geoapi.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://geosearch.dev
# See configuration.py for a list of all supported configuration parameters.
configuration = geoapi.Configuration(
    host = "https://geosearch.dev"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure API key authorization: apiKeyAuth
configuration.api_key['apiKeyAuth'] = os.environ["API_KEY"]

# Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
# configuration.api_key_prefix['apiKeyAuth'] = 'Bearer'

# Enter a context with an instance of the API client
with geoapi.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = geoapi.PostalCodesApi(api_client)
    lat = 37.7749 # float | Latitude (-90 to 90)
    lon = -122.4194 # float | Longitude (-180 to 180)
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    limit = 1 # int | Number of results (1-10, default 1) (optional) (default to 1)

    try:
        # Find nearest postal codes
        api_response = api_instance.nearest_postal_code(lat, lon, lang=lang, limit=limit)
        print("The response of PostalCodesApi->nearest_postal_code:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PostalCodesApi->nearest_postal_code: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lat** | **float**| Latitude (-90 to 90) | 
 **lon** | **float**| Longitude (-180 to 180) | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **limit** | **int**| Number of results (1-10, default 1) | [optional] [default to 1]

### Return type

[**PostalCodeListResponse**](PostalCodeListResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Nearest postal codes |  -  |
**400** | Invalid request parameters |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

