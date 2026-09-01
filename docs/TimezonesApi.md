# geoapi.TimezonesApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_timezone**](TimezonesApi.md#get_timezone) | **GET** /v1/timezones/{tzId} | Get timezone by IANA ID
[**list_timezones**](TimezonesApi.md#list_timezones) | **GET** /v1/timezones | List timezones


# **get_timezone**
> TimezoneSingleResponse get_timezone(tz_id, lang=lang, fields=fields)

Get timezone by IANA ID

Returns a single timezone by its IANA identifier.
Note: IANA timezone IDs contain slashes (e.g., America/New_York),
so the path uses a wildcard match.


### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.timezone_single_response import TimezoneSingleResponse
from geoapi.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = geoapi.Configuration(
    host = "http://localhost"
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
    api_instance = geoapi.TimezonesApi(api_client)
    tz_id = 'America/New_York' # str | IANA timezone ID (e.g., America/New_York)
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)

    try:
        # Get timezone by IANA ID
        api_response = api_instance.get_timezone(tz_id, lang=lang, fields=fields)
        print("The response of TimezonesApi->get_timezone:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling TimezonesApi->get_timezone: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **tz_id** | **str**| IANA timezone ID (e.g., America/New_York) | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 

### Return type

[**TimezoneSingleResponse**](TimezoneSingleResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Timezone details |  -  |
**400** | Invalid request parameters |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**404** | Resource not found |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_timezones**
> TimezoneListResponse list_timezones(lang=lang, country=country, cursor=cursor, limit=limit, fields=fields, sort=sort)

List timezones

Returns a paginated list of timezones with optional filtering by country.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.timezone_list_response import TimezoneListResponse
from geoapi.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = geoapi.Configuration(
    host = "http://localhost"
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
    api_instance = geoapi.TimezonesApi(api_client)
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    country = 'US' # str | Filter by ISO alpha-2 country code (optional)
    cursor = 'eyJpZCI6MjV9' # str | Pagination cursor from a previous response (optional)
    limit = 25 # int | Number of results per page (1-100, default 25) (optional) (default to 25)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)
    sort = 'gmt_offset' # str | Sort field. Allowed: timezone_id, gmt_offset, country_code. (optional)

    try:
        # List timezones
        api_response = api_instance.list_timezones(lang=lang, country=country, cursor=cursor, limit=limit, fields=fields, sort=sort)
        print("The response of TimezonesApi->list_timezones:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling TimezonesApi->list_timezones: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **country** | **str**| Filter by ISO alpha-2 country code | [optional] 
 **cursor** | **str**| Pagination cursor from a previous response | [optional] 
 **limit** | **int**| Number of results per page (1-100, default 25) | [optional] [default to 25]
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 
 **sort** | **str**| Sort field. Allowed: timezone_id, gmt_offset, country_code. | [optional] 

### Return type

[**TimezoneListResponse**](TimezoneListResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | List of timezones |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

