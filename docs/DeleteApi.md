# DeleteApi

All URIs are relative to *http://caravel.int.ingv.it/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteLocalspace**](DeleteApi.md#deleteLocalspace) | **DELETE** /quakedb/_table/v1/localspace/{id} | Delete an existing localspace |
| [**deleteTypeEvent**](DeleteApi.md#deleteTypeEvent) | **DELETE** /quakedb/_table/v1/type_event/{id} | Delete an existing type_event |
| [**deleteTypeMagnitude**](DeleteApi.md#deleteTypeMagnitude) | **DELETE** /quakedb/_table/v1/type_magnitude/{id} | Delete an existing type_magnitude |
| [**deleteTypeOrigin**](DeleteApi.md#deleteTypeOrigin) | **DELETE** /quakedb/_table/v1/type_origin/{id} | Delete an existing type_origin |


<a name="deleteLocalspace"></a>
# **deleteLocalspace**
> deleteLocalspace(id)

Delete an existing localspace

Delete an existing localspace.&lt;/br&gt; To use this API you must be authenticated.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.DeleteApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    DeleteApi apiInstance = new DeleteApi(defaultClient);
    Long id = 56L; // Long | INGV localspace id that need to be deleted.
    try {
      apiInstance.deleteLocalspace(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeleteApi#deleteLocalspace");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **Long**| INGV localspace id that need to be deleted. | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **204** | record deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="deleteTypeEvent"></a>
# **deleteTypeEvent**
> deleteTypeEvent(id)

Delete an existing type_event

Delete an existing type_event.&lt;/br&gt; To use this API you must be authenticated.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.DeleteApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    DeleteApi apiInstance = new DeleteApi(defaultClient);
    Long id = 56L; // Long | INGV type_event id that need to be deleted.
    try {
      apiInstance.deleteTypeEvent(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeleteApi#deleteTypeEvent");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **Long**| INGV type_event id that need to be deleted. | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **204** | record deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="deleteTypeMagnitude"></a>
# **deleteTypeMagnitude**
> deleteTypeMagnitude(id)

Delete an existing type_magnitude

Delete an existing type_magnitude.&lt;/br&gt; To use this API you must be authenticated.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.DeleteApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    DeleteApi apiInstance = new DeleteApi(defaultClient);
    Long id = 56L; // Long | INGV type_magnitude id that need to be deleted.
    try {
      apiInstance.deleteTypeMagnitude(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeleteApi#deleteTypeMagnitude");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **Long**| INGV type_magnitude id that need to be deleted. | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **204** | record deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="deleteTypeOrigin"></a>
# **deleteTypeOrigin**
> deleteTypeOrigin(id)

Delete an existing type_origin

Delete an existing type_origin.&lt;/br&gt; To use this API you must be authenticated.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.DeleteApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    DeleteApi apiInstance = new DeleteApi(defaultClient);
    Long id = 56L; // Long | INGV type_origin id that need to be deleted.
    try {
      apiInstance.deleteTypeOrigin(id);
    } catch (ApiException e) {
      System.err.println("Exception when calling DeleteApi#deleteTypeOrigin");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | **Long**| INGV type_origin id that need to be deleted. | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **204** | record deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

