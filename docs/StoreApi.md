# StoreApi

All URIs are relative to *https://caravel-dante.int.ingv.it/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addCatalog**](StoreApi.md#addCatalog) | **POST** /quakedb/v1/events-catalog | Add a new catalog to the DB |
| [**addEvent**](StoreApi.md#addEvent) | **POST** /quakedb/v1/event | Add a new event to the DB |
| [**addFocalmechanism**](StoreApi.md#addFocalmechanism) | **POST** /quakedb/v1/focalmechanism | Add a new focalmechanism(s) to the DB |
| [**addLocalspace**](StoreApi.md#addLocalspace) | **POST** /quakedb/table/v1/localspace | Add a new localspace to the DB |
| [**addMagnitude**](StoreApi.md#addMagnitude) | **POST** /quakedb/v1/magnitude | Add a new magnitude(s) to the DB |
| [**addMomenttensor**](StoreApi.md#addMomenttensor) | **POST** /quakedb/v1/momenttensor | Add a new momenttensor(s) to the DB |
| [**addOrigin**](StoreApi.md#addOrigin) | **POST** /quakedb/v1/origin | Add a new origin(s) to the DB |
| [**addOriginFlag**](StoreApi.md#addOriginFlag) | **POST** /quakedb/v1/origin-flag | Add one or more flags to origin |
| [**addProvenance**](StoreApi.md#addProvenance) | **POST** /quakedb/table/v1/provenance | Add a new provenance to the DB |
| [**addStrongmotion**](StoreApi.md#addStrongmotion) | **POST** /quakedb/v1/strongmotion | Add a new strongmotion(s) to the DB |
| [**addTypeEvent**](StoreApi.md#addTypeEvent) | **POST** /quakedb/table/v1/type-event | Add a new type_event to the DB |
| [**addTypeMagnitude**](StoreApi.md#addTypeMagnitude) | **POST** /quakedb/table/v1/type-magnitude | Add a new type_magnitude to the DB |
| [**addTypeOrigin**](StoreApi.md#addTypeOrigin) | **POST** /quakedb/table/v1/type-origin | Add a new type_origin to the DB |


<a name="addCatalog"></a>
# **addCatalog**
> AddCatalog201Response addCatalog(addCatalogRequest)

Add a new catalog to the DB

This API is used to add a catalog object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddCatalogRequest addCatalogRequest = new AddCatalogRequest(); // AddCatalogRequest | JSON to store
    try {
      AddCatalog201Response result = apiInstance.addCatalog(addCatalogRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addCatalog");
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
| **addCatalogRequest** | [**AddCatalogRequest**](AddCatalogRequest.md)| JSON to store | |

### Return type

[**AddCatalog201Response**](AddCatalog201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addEvent"></a>
# **addEvent**
> AddEvent201Response addEvent(getEvent200Response)

Add a new event to the DB

This API is used to add an event object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    GetEvent200Response getEvent200Response = new GetEvent200Response(); // GetEvent200Response | JSON to store
    try {
      AddEvent201Response result = apiInstance.addEvent(getEvent200Response);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addEvent");
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
| **getEvent200Response** | [**GetEvent200Response**](GetEvent200Response.md)| JSON to store | |

### Return type

[**AddEvent201Response**](AddEvent201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addFocalmechanism"></a>
# **addFocalmechanism**
> AddFocalmechanism201Response addFocalmechanism(addFocalmechanismRequest)

Add a new focalmechanism(s) to the DB

This API is used to add a focalmechanism object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddFocalmechanismRequest addFocalmechanismRequest = new AddFocalmechanismRequest(); // AddFocalmechanismRequest | JSON to store
    try {
      AddFocalmechanism201Response result = apiInstance.addFocalmechanism(addFocalmechanismRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addFocalmechanism");
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
| **addFocalmechanismRequest** | [**AddFocalmechanismRequest**](AddFocalmechanismRequest.md)| JSON to store | |

### Return type

[**AddFocalmechanism201Response**](AddFocalmechanism201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addLocalspace"></a>
# **addLocalspace**
> ObjectTableLocalspace addLocalspace(addLocalspaceRequest)

Add a new localspace to the DB

This API is used to add an localspace object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddLocalspaceRequest addLocalspaceRequest = new AddLocalspaceRequest(); // AddLocalspaceRequest | JSON to store
    try {
      ObjectTableLocalspace result = apiInstance.addLocalspace(addLocalspaceRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addLocalspace");
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
| **addLocalspaceRequest** | [**AddLocalspaceRequest**](AddLocalspaceRequest.md)| JSON to store | |

### Return type

[**ObjectTableLocalspace**](ObjectTableLocalspace.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addMagnitude"></a>
# **addMagnitude**
> AddMagnitude201Response addMagnitude(addMagnitudeRequest)

Add a new magnitude(s) to the DB

This API is used to add a magnitude object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddMagnitudeRequest addMagnitudeRequest = new AddMagnitudeRequest(); // AddMagnitudeRequest | JSON to store
    try {
      AddMagnitude201Response result = apiInstance.addMagnitude(addMagnitudeRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addMagnitude");
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
| **addMagnitudeRequest** | [**AddMagnitudeRequest**](AddMagnitudeRequest.md)| JSON to store | |

### Return type

[**AddMagnitude201Response**](AddMagnitude201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addMomenttensor"></a>
# **addMomenttensor**
> AddMomenttensor201Response addMomenttensor(addMomenttensorRequest)

Add a new momenttensor(s) to the DB

This API is used to add a momenttensor object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddMomenttensorRequest addMomenttensorRequest = new AddMomenttensorRequest(); // AddMomenttensorRequest | JSON to store
    try {
      AddMomenttensor201Response result = apiInstance.addMomenttensor(addMomenttensorRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addMomenttensor");
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
| **addMomenttensorRequest** | [**AddMomenttensorRequest**](AddMomenttensorRequest.md)| JSON to store | |

### Return type

[**AddMomenttensor201Response**](AddMomenttensor201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addOrigin"></a>
# **addOrigin**
> AddOrigin201Response addOrigin(addOriginRequest)

Add a new origin(s) to the DB

This API is used to add an origin object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddOriginRequest addOriginRequest = new AddOriginRequest(); // AddOriginRequest | JSON to store
    try {
      AddOrigin201Response result = apiInstance.addOrigin(addOriginRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addOrigin");
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
| **addOriginRequest** | [**AddOriginRequest**](AddOriginRequest.md)| JSON to store | |

### Return type

[**AddOrigin201Response**](AddOrigin201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addOriginFlag"></a>
# **addOriginFlag**
> AddOriginFlag201Response addOriginFlag(addOriginFlagRequest)

Add one or more flags to origin

This API is used to add one or more flags to origin.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddOriginFlagRequest addOriginFlagRequest = new AddOriginFlagRequest(); // AddOriginFlagRequest | JSON to store
    try {
      AddOriginFlag201Response result = apiInstance.addOriginFlag(addOriginFlagRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addOriginFlag");
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
| **addOriginFlagRequest** | [**AddOriginFlagRequest**](AddOriginFlagRequest.md)| JSON to store | |

### Return type

[**AddOriginFlag201Response**](AddOriginFlag201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addProvenance"></a>
# **addProvenance**
> ObjectTableProvenance addProvenance(addProvenanceRequest)

Add a new provenance to the DB

This API is used to add an provenance object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddProvenanceRequest addProvenanceRequest = new AddProvenanceRequest(); // AddProvenanceRequest | JSON to store
    try {
      ObjectTableProvenance result = apiInstance.addProvenance(addProvenanceRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addProvenance");
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
| **addProvenanceRequest** | [**AddProvenanceRequest**](AddProvenanceRequest.md)| JSON to store | |

### Return type

[**ObjectTableProvenance**](ObjectTableProvenance.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addStrongmotion"></a>
# **addStrongmotion**
> AddStrongmotion201Response addStrongmotion(addStrongmotionRequest)

Add a new strongmotion(s) to the DB

This API is used to add a strongmotion object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddStrongmotionRequest addStrongmotionRequest = new AddStrongmotionRequest(); // AddStrongmotionRequest | JSON to store
    try {
      AddStrongmotion201Response result = apiInstance.addStrongmotion(addStrongmotionRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addStrongmotion");
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
| **addStrongmotionRequest** | [**AddStrongmotionRequest**](AddStrongmotionRequest.md)| JSON to store | |

### Return type

[**AddStrongmotion201Response**](AddStrongmotion201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addTypeEvent"></a>
# **addTypeEvent**
> ObjectTableTypeEvent addTypeEvent(addTypeEventRequest)

Add a new type_event to the DB

This API is used to add an type_event object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddTypeEventRequest addTypeEventRequest = new AddTypeEventRequest(); // AddTypeEventRequest | JSON to store
    try {
      ObjectTableTypeEvent result = apiInstance.addTypeEvent(addTypeEventRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addTypeEvent");
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
| **addTypeEventRequest** | [**AddTypeEventRequest**](AddTypeEventRequest.md)| JSON to store | |

### Return type

[**ObjectTableTypeEvent**](ObjectTableTypeEvent.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addTypeMagnitude"></a>
# **addTypeMagnitude**
> ObjectTableTypeMagnitude addTypeMagnitude(addTypeMagnitudeRequest)

Add a new type_magnitude to the DB

This API is used to add an type_magnitude object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddTypeMagnitudeRequest addTypeMagnitudeRequest = new AddTypeMagnitudeRequest(); // AddTypeMagnitudeRequest | JSON to store
    try {
      ObjectTableTypeMagnitude result = apiInstance.addTypeMagnitude(addTypeMagnitudeRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addTypeMagnitude");
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
| **addTypeMagnitudeRequest** | [**AddTypeMagnitudeRequest**](AddTypeMagnitudeRequest.md)| JSON to store | |

### Return type

[**ObjectTableTypeMagnitude**](ObjectTableTypeMagnitude.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="addTypeOrigin"></a>
# **addTypeOrigin**
> ObjectTableTypeOrigin addTypeOrigin(addTypeOriginRequest)

Add a new type_origin to the DB

This API is used to add an type_origin object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.auth.*;
import org.ingv.dante.models.*;
import org.ingv.dante.api.StoreApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");
    
    // Configure HTTP bearer authorization: BearerAuth
    HttpBearerAuth BearerAuth = (HttpBearerAuth) defaultClient.getAuthentication("BearerAuth");
    BearerAuth.setBearerToken("BEARER TOKEN");

    StoreApi apiInstance = new StoreApi(defaultClient);
    AddTypeOriginRequest addTypeOriginRequest = new AddTypeOriginRequest(); // AddTypeOriginRequest | JSON to store
    try {
      ObjectTableTypeOrigin result = apiInstance.addTypeOrigin(addTypeOriginRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling StoreApi#addTypeOrigin");
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
| **addTypeOriginRequest** | [**AddTypeOriginRequest**](AddTypeOriginRequest.md)| JSON to store | |

### Return type

[**ObjectTableTypeOrigin**](ObjectTableTypeOrigin.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **201** | record inserted |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

