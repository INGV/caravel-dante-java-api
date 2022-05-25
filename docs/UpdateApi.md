# UpdateApi

All URIs are relative to *http://caravel.int.ingv.it/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**updateEvent**](UpdateApi.md#updateEvent) | **PATCH** /quakedb/v1/event/{id} | Update an existing event |
| [**updateLocalspace**](UpdateApi.md#updateLocalspace) | **PATCH** /quakedb/_table/v1/localspace/{id} | Update an existing localspace |
| [**updateOriginFlag**](UpdateApi.md#updateOriginFlag) | **PATCH** /quakedb/v1/origin-flag/{id} | Update an existing origin-flag |
| [**updateTypeEvent**](UpdateApi.md#updateTypeEvent) | **PATCH** /quakedb/_table/v1/type_event/{id} | Update an existing type_event |
| [**updateTypeMagnitude**](UpdateApi.md#updateTypeMagnitude) | **PATCH** /quakedb/_table/v1/type_magnitude/{id} | Update an existing type_magnitude |
| [**updateTypeOrigin**](UpdateApi.md#updateTypeOrigin) | **PATCH** /quakedb/_table/v1/type_origin/{id} | Update an existing type_origin |


<a name="updateEvent"></a>
# **updateEvent**
> updateEvent(id, updateEventRequest)

Update an existing event

Update an existing event.&lt;/br&gt; To use this API you must be authenticated and \&quot;event.localspace_name\&quot; owner.&lt;/br&gt; More info about &#x60;event_group_id&#x60; &lt;b&gt;https://gitlab.rm.ingv.it/caravel/dante8/-/issues/69#note_60479&lt;/b&gt;

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.UpdateApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    UpdateApi apiInstance = new UpdateApi(defaultClient);
    Long id = 56L; // Long | INGV eventid that need to be updated.
    UpdateEventRequest updateEventRequest = new UpdateEventRequest(); // UpdateEventRequest | JSON to update
    try {
      apiInstance.updateEvent(id, updateEventRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling UpdateApi#updateEvent");
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
| **id** | **Long**| INGV eventid that need to be updated. | |
| **updateEventRequest** | [**UpdateEventRequest**](UpdateEventRequest.md)| JSON to update | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateLocalspace"></a>
# **updateLocalspace**
> updateLocalspace(id, addLocalspaceRequest)

Update an existing localspace

Update an existing localspace.&lt;/br&gt; To use this API you must be authenticated.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.UpdateApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    UpdateApi apiInstance = new UpdateApi(defaultClient);
    Long id = 56L; // Long | INGV localspace id that need to be updated.
    AddLocalspaceRequest addLocalspaceRequest = new AddLocalspaceRequest(); // AddLocalspaceRequest | JSON to update
    try {
      apiInstance.updateLocalspace(id, addLocalspaceRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling UpdateApi#updateLocalspace");
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
| **id** | **Long**| INGV localspace id that need to be updated. | |
| **addLocalspaceRequest** | [**AddLocalspaceRequest**](AddLocalspaceRequest.md)| JSON to update | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateOriginFlag"></a>
# **updateOriginFlag**
> updateOriginFlag(id, updateOriginFlagRequest)

Update an existing origin-flag

Update an existing origin-flag.&lt;/br&gt; To use this API you must be authenticated and \&quot;origin.localspace_name\&quot; owner.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.UpdateApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    UpdateApi apiInstance = new UpdateApi(defaultClient);
    Long id = 56L; // Long | INGV origin-flag id that need to be updated.
    UpdateOriginFlagRequest updateOriginFlagRequest = new UpdateOriginFlagRequest(); // UpdateOriginFlagRequest | JSON to update
    try {
      apiInstance.updateOriginFlag(id, updateOriginFlagRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling UpdateApi#updateOriginFlag");
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
| **id** | **Long**| INGV origin-flag id that need to be updated. | |
| **updateOriginFlagRequest** | [**UpdateOriginFlagRequest**](UpdateOriginFlagRequest.md)| JSON to update | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateTypeEvent"></a>
# **updateTypeEvent**
> updateTypeEvent(id, addTypeEventRequest)

Update an existing type_event

Update an existing type_event.&lt;/br&gt; To use this API you must be authenticated.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.UpdateApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    UpdateApi apiInstance = new UpdateApi(defaultClient);
    Long id = 56L; // Long | INGV type_event id that need to be updated.
    AddTypeEventRequest addTypeEventRequest = new AddTypeEventRequest(); // AddTypeEventRequest | JSON to update
    try {
      apiInstance.updateTypeEvent(id, addTypeEventRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling UpdateApi#updateTypeEvent");
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
| **id** | **Long**| INGV type_event id that need to be updated. | |
| **addTypeEventRequest** | [**AddTypeEventRequest**](AddTypeEventRequest.md)| JSON to update | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateTypeMagnitude"></a>
# **updateTypeMagnitude**
> updateTypeMagnitude(id, addTypeMagnitudeRequest)

Update an existing type_magnitude

Update an existing type_magnitude.&lt;/br&gt; To use this API you must be authenticated.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.UpdateApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    UpdateApi apiInstance = new UpdateApi(defaultClient);
    Long id = 56L; // Long | INGV type_magnitude id that need to be updated.
    AddTypeMagnitudeRequest addTypeMagnitudeRequest = new AddTypeMagnitudeRequest(); // AddTypeMagnitudeRequest | JSON to update
    try {
      apiInstance.updateTypeMagnitude(id, addTypeMagnitudeRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling UpdateApi#updateTypeMagnitude");
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
| **id** | **Long**| INGV type_magnitude id that need to be updated. | |
| **addTypeMagnitudeRequest** | [**AddTypeMagnitudeRequest**](AddTypeMagnitudeRequest.md)| JSON to update | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateTypeOrigin"></a>
# **updateTypeOrigin**
> updateTypeOrigin(id, addTypeOriginRequest)

Update an existing type_origin

Update an existing type_origin.&lt;/br&gt; To use this API you must be authenticated.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.UpdateApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    UpdateApi apiInstance = new UpdateApi(defaultClient);
    Long id = 56L; // Long | INGV type_origin id that need to be updated.
    AddTypeOriginRequest addTypeOriginRequest = new AddTypeOriginRequest(); // AddTypeOriginRequest | JSON to update
    try {
      apiInstance.updateTypeOrigin(id, addTypeOriginRequest);
    } catch (ApiException e) {
      System.err.println("Exception when calling UpdateApi#updateTypeOrigin");
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
| **id** | **Long**| INGV type_origin id that need to be updated. | |
| **addTypeOriginRequest** | [**AddTypeOriginRequest**](AddTypeOriginRequest.md)| JSON to update | |

### Return type

null (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

