# UpdateApi

All URIs are relative to *http://caravel.int.ingv.it/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**updateEvent**](UpdateApi.md#updateEvent) | **PATCH** /quakedb/v1/event/{id} | Update an existing event |
| [**updateLocalspace**](UpdateApi.md#updateLocalspace) | **PATCH** /quakedb/table/v1/localspace/{id} | Update an existing localspace |
| [**updateOriginFlag**](UpdateApi.md#updateOriginFlag) | **PATCH** /quakedb/v1/origin-flag/{id} | Update an existing origin-flag |
| [**updateProvenance**](UpdateApi.md#updateProvenance) | **PATCH** /quakedb/table/v1/provenance/{id} | Update an existing provenance |
| [**updateTypeEvent**](UpdateApi.md#updateTypeEvent) | **PATCH** /quakedb/table/v1/type-event/{id} | Update an existing type_event |
| [**updateTypeMagnitude**](UpdateApi.md#updateTypeMagnitude) | **PATCH** /quakedb/table/v1/type-magnitude/{id} | Update an existing type_magnitude |
| [**updateTypeOrigin**](UpdateApi.md#updateTypeOrigin) | **PATCH** /quakedb/table/v1/type-origin/{id} | Update an existing type_origin |


<a name="updateEvent"></a>
# **updateEvent**
> Object updateEvent(id, UNKNOWN_BASE_TYPE)

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
    UNKNOWN_BASE_TYPE UNKNOWN_BASE_TYPE = new UNKNOWN_BASE_TYPE(); // UNKNOWN_BASE_TYPE | JSON to update
    try {
      Object result = apiInstance.updateEvent(id, UNKNOWN_BASE_TYPE);
      System.out.println(result);
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
| **UNKNOWN_BASE_TYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| JSON to update | |

### Return type

**Object**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateLocalspace"></a>
# **updateLocalspace**
> ObjectTableLocalspace updateLocalspace(id, objectTableLocalspace)

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
    ObjectTableLocalspace objectTableLocalspace = new ObjectTableLocalspace(); // ObjectTableLocalspace | JSON to update
    try {
      ObjectTableLocalspace result = apiInstance.updateLocalspace(id, objectTableLocalspace);
      System.out.println(result);
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
| **objectTableLocalspace** | [**ObjectTableLocalspace**](ObjectTableLocalspace.md)| JSON to update | |

### Return type

[**ObjectTableLocalspace**](ObjectTableLocalspace.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateOriginFlag"></a>
# **updateOriginFlag**
> Object updateOriginFlag(id, UNKNOWN_BASE_TYPE)

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
    UNKNOWN_BASE_TYPE UNKNOWN_BASE_TYPE = new UNKNOWN_BASE_TYPE(); // UNKNOWN_BASE_TYPE | JSON to update
    try {
      Object result = apiInstance.updateOriginFlag(id, UNKNOWN_BASE_TYPE);
      System.out.println(result);
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
| **UNKNOWN_BASE_TYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| JSON to update | |

### Return type

**Object**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateProvenance"></a>
# **updateProvenance**
> ObjectTableProvenance updateProvenance(id, objectTableProvenance)

Update an existing provenance

Update an existing provenance.&lt;/br&gt; To use this API you must be authenticated.

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
    Long id = 56L; // Long | INGV provenance id that need to be updated.
    ObjectTableProvenance objectTableProvenance = new ObjectTableProvenance(); // ObjectTableProvenance | JSON to update
    try {
      ObjectTableProvenance result = apiInstance.updateProvenance(id, objectTableProvenance);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling UpdateApi#updateProvenance");
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
| **id** | **Long**| INGV provenance id that need to be updated. | |
| **objectTableProvenance** | [**ObjectTableProvenance**](ObjectTableProvenance.md)| JSON to update | |

### Return type

[**ObjectTableProvenance**](ObjectTableProvenance.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateTypeEvent"></a>
# **updateTypeEvent**
> ObjectTableTypeEvent updateTypeEvent(id, objectTableTypeEvent)

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
    ObjectTableTypeEvent objectTableTypeEvent = new ObjectTableTypeEvent(); // ObjectTableTypeEvent | JSON to update
    try {
      ObjectTableTypeEvent result = apiInstance.updateTypeEvent(id, objectTableTypeEvent);
      System.out.println(result);
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
| **objectTableTypeEvent** | [**ObjectTableTypeEvent**](ObjectTableTypeEvent.md)| JSON to update | |

### Return type

[**ObjectTableTypeEvent**](ObjectTableTypeEvent.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateTypeMagnitude"></a>
# **updateTypeMagnitude**
> ObjectTableTypeMagnitude updateTypeMagnitude(id, objectTableTypeMagnitude)

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
    ObjectTableTypeMagnitude objectTableTypeMagnitude = new ObjectTableTypeMagnitude(); // ObjectTableTypeMagnitude | JSON to update
    try {
      ObjectTableTypeMagnitude result = apiInstance.updateTypeMagnitude(id, objectTableTypeMagnitude);
      System.out.println(result);
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
| **objectTableTypeMagnitude** | [**ObjectTableTypeMagnitude**](ObjectTableTypeMagnitude.md)| JSON to update | |

### Return type

[**ObjectTableTypeMagnitude**](ObjectTableTypeMagnitude.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

<a name="updateTypeOrigin"></a>
# **updateTypeOrigin**
> ObjectTableTypeOrigin updateTypeOrigin(id, objectTableTypeOrigin)

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
    ObjectTableTypeOrigin objectTableTypeOrigin = new ObjectTableTypeOrigin(); // ObjectTableTypeOrigin | JSON to update
    try {
      ObjectTableTypeOrigin result = apiInstance.updateTypeOrigin(id, objectTableTypeOrigin);
      System.out.println(result);
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
| **objectTableTypeOrigin** | [**ObjectTableTypeOrigin**](ObjectTableTypeOrigin.md)| JSON to update | |

### Return type

[**ObjectTableTypeOrigin**](ObjectTableTypeOrigin.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/merge-patch+json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | record updated |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **0** | Unexpected error |  -  |

