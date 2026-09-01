# geoapi.HealthApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_status**](HealthApi.md#get_status) | **GET** /v1/status | Health check


# **get_status**
> GetStatus200Response get_status()

Health check

Returns the API health status and database connectivity. No authentication required.

### Example


```python
import geoapi
from geoapi.models.get_status200_response import GetStatus200Response
from geoapi.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = geoapi.Configuration(
    host = "http://localhost"
)


# Enter a context with an instance of the API client
with geoapi.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = geoapi.HealthApi(api_client)

    try:
        # Health check
        api_response = api_instance.get_status()
        print("The response of HealthApi->get_status:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling HealthApi->get_status: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**GetStatus200Response**](GetStatus200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | API status |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

