# geoapi.RegionsApi

All URIs are relative to *https://geosearch.dev*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_region**](RegionsApi.md#get_region) | **GET** /v1/regions/{id} | Get region by ID
[**list_region_cities**](RegionsApi.md#list_region_cities) | **GET** /v1/regions/{id}/cities | List cities in a region
[**list_regions**](RegionsApi.md#list_regions) | **GET** /v1/regions | List regions
[**region_children**](RegionsApi.md#region_children) | **GET** /v1/regions/{id}/children | List child cities of a region


# **get_region**
> RegionSingleResponse get_region(id, lang=lang, fields=fields)

Get region by ID

Returns a single region by its numeric ID.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.region_single_response import RegionSingleResponse
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
    api_instance = geoapi.RegionsApi(api_client)
    id = 5332921 # int | Region ID
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)

    try:
        # Get region by ID
        api_response = api_instance.get_region(id, lang=lang, fields=fields)
        print("The response of RegionsApi->get_region:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RegionsApi->get_region: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| Region ID | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 

### Return type

[**RegionSingleResponse**](RegionSingleResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Region details |  -  |
**400** | Invalid request parameters |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**404** | Resource not found |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_region_cities**
> CityListResponse list_region_cities(id, lang=lang, cursor=cursor, limit=limit, fields=fields, sort=sort)

List cities in a region

Returns a paginated list of cities within a specific region.

THIS ENDPOINT AND `/v1/cities?within=` ANSWER DIFFERENT QUESTIONS AND WILL SOMETIMES RETURN DIFFERENT CITIES FOR THE SAME REGION. That is intended, not a bug. This endpoint answers the ADMINISTRATIVE question — which cities are assigned to this region by GeoNames' own admin codes — while `?within=` answers the GEOMETRIC one, which cities fall inside the region's polygon. The two disagree wherever an enclave, an exclave or a blank admin code puts a city's assignment at odds with its location.

Use this endpoint when you want the official assignment; use `/v1/cities?within=` when you want what is physically inside the boundary. This one is charged at the standard 1 unit; `?within=` costs 2.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.city_list_response import CityListResponse
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
    api_instance = geoapi.RegionsApi(api_client)
    id = 5332921 # int | Region ID
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    cursor = 'eyJpZCI6MjV9' # str | Pagination cursor from a previous response (optional)
    limit = 25 # int | Number of results per page (1-100, default 25) (optional) (default to 25)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)
    sort = '-population' # str | Sort field. Allowed: name, population. (optional)

    try:
        # List cities in a region
        api_response = api_instance.list_region_cities(id, lang=lang, cursor=cursor, limit=limit, fields=fields, sort=sort)
        print("The response of RegionsApi->list_region_cities:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RegionsApi->list_region_cities: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| Region ID | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **cursor** | **str**| Pagination cursor from a previous response | [optional] 
 **limit** | **int**| Number of results per page (1-100, default 25) | [optional] [default to 25]
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 
 **sort** | **str**| Sort field. Allowed: name, population. | [optional] 

### Return type

[**CityListResponse**](CityListResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of cities |  -  |
**400** | Invalid request parameters |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_regions**
> RegionListResponse list_regions(lang=lang, country=country, level=level, population_min=population_min, population_max=population_max, cursor=cursor, limit=limit, fields=fields, sort=sort)

List regions

Returns a paginated list of regions with optional filtering by country, level, and population.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.region_list_response import RegionListResponse
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
    api_instance = geoapi.RegionsApi(api_client)
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    country = 'US' # str | Filter by ISO alpha-2 country code (optional)
    level = 1 # int | Filter by administrative level (optional)
    population_min = 1000000 # int | Minimum population filter (optional)
    population_max = 10000000 # int | Maximum population filter (optional)
    cursor = 'eyJpZCI6MjV9' # str | Pagination cursor from a previous response (optional)
    limit = 25 # int | Number of results per page (1-100, default 25) (optional) (default to 25)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)
    sort = '-population' # str | Sort field. Allowed: name, population. (optional)

    try:
        # List regions
        api_response = api_instance.list_regions(lang=lang, country=country, level=level, population_min=population_min, population_max=population_max, cursor=cursor, limit=limit, fields=fields, sort=sort)
        print("The response of RegionsApi->list_regions:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RegionsApi->list_regions: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **country** | **str**| Filter by ISO alpha-2 country code | [optional] 
 **level** | **int**| Filter by administrative level | [optional] 
 **population_min** | **int**| Minimum population filter | [optional] 
 **population_max** | **int**| Maximum population filter | [optional] 
 **cursor** | **str**| Pagination cursor from a previous response | [optional] 
 **limit** | **int**| Number of results per page (1-100, default 25) | [optional] [default to 25]
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 
 **sort** | **str**| Sort field. Allowed: name, population. | [optional] 

### Return type

[**RegionListResponse**](RegionListResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of regions |  -  |
**400** | Invalid request parameters |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **region_children**
> CityListResponse region_children(id, lang=lang, fields=fields)

List child cities of a region

Returns all cities that are direct children of the specified region in the administrative hierarchy.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.city_list_response import CityListResponse
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
    api_instance = geoapi.RegionsApi(api_client)
    id = 5332921 # int | Region ID
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)

    try:
        # List child cities of a region
        api_response = api_instance.region_children(id, lang=lang, fields=fields)
        print("The response of RegionsApi->region_children:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling RegionsApi->region_children: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| Region ID | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 

### Return type

[**CityListResponse**](CityListResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of child cities |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**404** | Resource not found |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

