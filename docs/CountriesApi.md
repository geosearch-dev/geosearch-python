# geoapi.CountriesApi

All URIs are relative to *https://geosearch.dev*

Method | HTTP request | Description
------------- | ------------- | -------------
[**country_neighbors**](CountriesApi.md#country_neighbors) | **GET** /v1/countries/{code}/neighbors | List neighboring countries
[**get_country**](CountriesApi.md#get_country) | **GET** /v1/countries/{code} | Get country by ISO code
[**list_countries**](CountriesApi.md#list_countries) | **GET** /v1/countries | List countries
[**list_country_regions**](CountriesApi.md#list_country_regions) | **GET** /v1/countries/{code}/regions | List regions in a country


# **country_neighbors**
> CountryListResponse country_neighbors(code, lang=lang, fields=fields)

List neighboring countries

Returns countries that share a border with the specified country.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.country_list_response import CountryListResponse
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
    api_instance = geoapi.CountriesApi(api_client)
    code = 'DE' # str | ISO alpha-2 country code
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)

    try:
        # List neighboring countries
        api_response = api_instance.country_neighbors(code, lang=lang, fields=fields)
        print("The response of CountriesApi->country_neighbors:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CountriesApi->country_neighbors: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **code** | **str**| ISO alpha-2 country code | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 

### Return type

[**CountryListResponse**](CountryListResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of neighboring countries |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**404** | Resource not found |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_country**
> CountrySingleResponse get_country(code, lang=lang, fields=fields)

Get country by ISO code

Returns a single country by its ISO alpha-2 code.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.country_single_response import CountrySingleResponse
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
    api_instance = geoapi.CountriesApi(api_client)
    code = 'US' # str | ISO alpha-2 country code
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)

    try:
        # Get country by ISO code
        api_response = api_instance.get_country(code, lang=lang, fields=fields)
        print("The response of CountriesApi->get_country:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CountriesApi->get_country: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **code** | **str**| ISO alpha-2 country code | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 

### Return type

[**CountrySingleResponse**](CountrySingleResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Country details |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**404** | Resource not found |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_countries**
> CountryListResponse list_countries(lang=lang, continent=continent, iso_code=iso_code, population_min=population_min, population_max=population_max, cursor=cursor, limit=limit, fields=fields, sort=sort)

List countries

Returns a paginated list of countries with optional filtering and sorting.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.country_list_response import CountryListResponse
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
    api_instance = geoapi.CountriesApi(api_client)
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    continent = 'EU' # str | Filter by continent code (AF, AN, AS, EU, NA, OC, SA) (optional)
    iso_code = 'US,CA,GB' # str | Filter by ISO alpha-2 codes (comma-separated) (optional)
    population_min = 1000000 # int | Minimum population filter (optional)
    population_max = 10000000 # int | Maximum population filter (optional)
    cursor = 'eyJpZCI6MjV9' # str | Pagination cursor from a previous response (optional)
    limit = 25 # int | Number of results per page (1-100, default 25) (optional) (default to 25)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)
    sort = '-population' # str | Sort field and direction. Allowed: name, population, area_sq_km. Prefix with - for descending. (optional)

    try:
        # List countries
        api_response = api_instance.list_countries(lang=lang, continent=continent, iso_code=iso_code, population_min=population_min, population_max=population_max, cursor=cursor, limit=limit, fields=fields, sort=sort)
        print("The response of CountriesApi->list_countries:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CountriesApi->list_countries: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **continent** | **str**| Filter by continent code (AF, AN, AS, EU, NA, OC, SA) | [optional] 
 **iso_code** | **str**| Filter by ISO alpha-2 codes (comma-separated) | [optional] 
 **population_min** | **int**| Minimum population filter | [optional] 
 **population_max** | **int**| Maximum population filter | [optional] 
 **cursor** | **str**| Pagination cursor from a previous response | [optional] 
 **limit** | **int**| Number of results per page (1-100, default 25) | [optional] [default to 25]
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 
 **sort** | **str**| Sort field and direction. Allowed: name, population, area_sq_km. Prefix with - for descending. | [optional] 

### Return type

[**CountryListResponse**](CountryListResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of countries |  -  |
**400** | Invalid request parameters |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_country_regions**
> RegionListResponse list_country_regions(code, lang=lang, cursor=cursor, limit=limit, fields=fields, sort=sort)

List regions in a country

Returns a paginated list of regions (administrative divisions) within a country.

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
    api_instance = geoapi.CountriesApi(api_client)
    code = 'US' # str | ISO alpha-2 country code
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    cursor = 'eyJpZCI6MjV9' # str | Pagination cursor from a previous response (optional)
    limit = 25 # int | Number of results per page (1-100, default 25) (optional) (default to 25)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)
    sort = 'name' # str | Sort field. Allowed: name, population. (optional)

    try:
        # List regions in a country
        api_response = api_instance.list_country_regions(code, lang=lang, cursor=cursor, limit=limit, fields=fields, sort=sort)
        print("The response of CountriesApi->list_country_regions:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CountriesApi->list_country_regions: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **code** | **str**| ISO alpha-2 country code | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
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
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

