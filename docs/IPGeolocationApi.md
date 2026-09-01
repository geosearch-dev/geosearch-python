# geoapi.IPGeolocationApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**lookup_ip**](IPGeolocationApi.md#lookup_ip) | **GET** /v1/ip/{address} | IP geolocation lookup
[**lookup_my_ip**](IPGeolocationApi.md#lookup_my_ip) | **GET** /v1/ip/me | Caller&#39;s IP geolocation


# **lookup_ip**
> IPSingleResponse lookup_ip(address, lang=lang, fields=fields)

IP geolocation lookup

Returns geolocation data for a given IPv4 or IPv6 address.

### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.ip_single_response import IPSingleResponse
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
    api_instance = geoapi.IPGeolocationApi(api_client)
    address = '8.8.8.8' # str | IPv4 or IPv6 address
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)

    try:
        # IP geolocation lookup
        api_response = api_instance.lookup_ip(address, lang=lang, fields=fields)
        print("The response of IPGeolocationApi->lookup_ip:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IPGeolocationApi->lookup_ip: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **address** | **str**| IPv4 or IPv6 address | 
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 

### Return type

[**IPSingleResponse**](IPSingleResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | IP geolocation result |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**422** | Invalid IP address format |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **lookup_my_ip**
> IPSingleResponse lookup_my_ip(lang=lang, fields=fields)

Caller's IP geolocation

Auto-detects the client's IP address (from X-Forwarded-For or RemoteAddr)
and returns its geolocation data.


### Example

* Api Key Authentication (apiKeyAuth):

```python
import geoapi
from geoapi.models.ip_single_response import IPSingleResponse
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
    api_instance = geoapi.IPGeolocationApi(api_client)
    lang = 'de' # str | ISO 639-1 language code for localized names (e.g., de, fr, ja) (optional)
    fields = 'name,population,iso_code' # str | Comma-separated list of fields to include in the response (optional)

    try:
        # Caller's IP geolocation
        api_response = api_instance.lookup_my_ip(lang=lang, fields=fields)
        print("The response of IPGeolocationApi->lookup_my_ip:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling IPGeolocationApi->lookup_my_ip: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **lang** | **str**| ISO 639-1 language code for localized names (e.g., de, fr, ja) | [optional] 
 **fields** | **str**| Comma-separated list of fields to include in the response | [optional] 

### Return type

[**IPSingleResponse**](IPSingleResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Caller&#39;s IP geolocation result |  -  |
**401** | Missing or invalid API key. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;authentication_required&#x60; means no key was supplied at all, and &#x60;authentication_failed&#x60; means a key was supplied and is not valid.  The distinction is worth branching on, because the remedies differ: the first is \&quot;sign up and send a key\&quot;, the second is \&quot;the key you sent is wrong, revoked or mistyped\&quot;. |  -  |
**429** | Rate limit exceeded. Distinguish the two cases by &#x60;error.code&#x60;: &#x60;rate_limit_exceeded&#x60; is the per-second throttle and clears within a second; &#x60;quota_exceeded&#x60; is the monthly allowance and carries an &#x60;error.quota&#x60; object describing the limit, the usage, the period end and where to upgrade. |  * X-RateLimit-Limit - Requests per second allowed <br>  * X-RateLimit-Remaining - Requests remaining in current window <br>  * X-RateLimit-Reset - Unix epoch second at which the limit that tripped resets. An absolute timestamp, not a duration. For &#x60;rate_limit_exceeded&#x60; this is the next per-second window boundary; for &#x60;quota_exceeded&#x60; it is the end of the monthly quota period and may be weeks away. <br>  * Retry-After - Seconds to wait before retrying. Sent on both 429 codes; only its magnitude differs — around a second for the throttle, up to the remainder of the billing period for the quota wall. Floored at 1, so it never instructs a client to retry immediately. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

