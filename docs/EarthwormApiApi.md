# EarthwormApiApi

All URIs are relative to *https://caravel-dante.int.ingv.it/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addEwHyp2000arc**](EarthwormApiApi.md#addEwHyp2000arc) | **POST** /quakedb/ew/v1/hyp2000arc | Insert a new hyp2000arc message to the DB using ew2openapi module |
| [**addEwQuake2k**](EarthwormApiApi.md#addEwQuake2k) | **POST** /quakedb/ew/v1/quake2k | Insert a new quake2k message to the DB using ew2openapi module |
| [**addHEwMagnitude**](EarthwormApiApi.md#addHEwMagnitude) | **POST** /quakedb/ew/v1/magnitude | Insert a new magnitude message to the DB using ew2openapi module |
| [**addHEwPickScnl**](EarthwormApiApi.md#addHEwPickScnl) | **POST** /quakedb/ew/v1/pick-scnl | Insert a new pick-scnl message to the DB using ew2openapi module |
| [**addHEwStrongmotionii**](EarthwormApiApi.md#addHEwStrongmotionii) | **POST** /quakedb/ew/v1/strongmotionii | Insert a new strongmotionii message to the DB using ew2openapi module |


<a id="addEwHyp2000arc"></a>
# **addEwHyp2000arc**
> AddEwHyp2000arc201Response addEwHyp2000arc(addEwHyp2000arcRequest)

Insert a new hyp2000arc message to the DB using ew2openapi module

This API is used to add an Earthworm hyp2000arc object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.EarthwormApiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    EarthwormApiApi apiInstance = new EarthwormApiApi(defaultClient);
    AddEwHyp2000arcRequest addEwHyp2000arcRequest = new AddEwHyp2000arcRequest(); // AddEwHyp2000arcRequest | JSON to store
    try {
      AddEwHyp2000arc201Response result = apiInstance.addEwHyp2000arc(addEwHyp2000arcRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EarthwormApiApi#addEwHyp2000arc");
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
| **addEwHyp2000arcRequest** | [**AddEwHyp2000arcRequest**](AddEwHyp2000arcRequest.md)| JSON to store | |

### Return type

[**AddEwHyp2000arc201Response**](AddEwHyp2000arc201Response.md)

### Authorization

No authorization required

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

<a id="addEwQuake2k"></a>
# **addEwQuake2k**
> UpdateEvent200Response addEwQuake2k(addEwQuake2kRequest)

Insert a new quake2k message to the DB using ew2openapi module

This API is used to add an Earthworm quake2k object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.EarthwormApiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    EarthwormApiApi apiInstance = new EarthwormApiApi(defaultClient);
    AddEwQuake2kRequest addEwQuake2kRequest = new AddEwQuake2kRequest(); // AddEwQuake2kRequest | JSON to store
    try {
      UpdateEvent200Response result = apiInstance.addEwQuake2k(addEwQuake2kRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EarthwormApiApi#addEwQuake2k");
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
| **addEwQuake2kRequest** | [**AddEwQuake2kRequest**](AddEwQuake2kRequest.md)| JSON to store | |

### Return type

[**UpdateEvent200Response**](UpdateEvent200Response.md)

### Authorization

No authorization required

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
| **201** | record insertedd |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="addHEwMagnitude"></a>
# **addHEwMagnitude**
> AddMagnitude201Response addHEwMagnitude(addHEwMagnitudeRequest)

Insert a new magnitude message to the DB using ew2openapi module

This API is used to add an Earthworm magnitude object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.EarthwormApiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    EarthwormApiApi apiInstance = new EarthwormApiApi(defaultClient);
    AddHEwMagnitudeRequest addHEwMagnitudeRequest = new AddHEwMagnitudeRequest(); // AddHEwMagnitudeRequest | JSON to store
    try {
      AddMagnitude201Response result = apiInstance.addHEwMagnitude(addHEwMagnitudeRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EarthwormApiApi#addHEwMagnitude");
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
| **addHEwMagnitudeRequest** | [**AddHEwMagnitudeRequest**](AddHEwMagnitudeRequest.md)| JSON to store | |

### Return type

[**AddMagnitude201Response**](AddMagnitude201Response.md)

### Authorization

No authorization required

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

<a id="addHEwPickScnl"></a>
# **addHEwPickScnl**
> AddHEwPickScnl201Response addHEwPickScnl(addHEwPickScnlRequest)

Insert a new pick-scnl message to the DB using ew2openapi module

This API is used to add an Earthworm pick_scnl object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.EarthwormApiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    EarthwormApiApi apiInstance = new EarthwormApiApi(defaultClient);
    AddHEwPickScnlRequest addHEwPickScnlRequest = new AddHEwPickScnlRequest(); // AddHEwPickScnlRequest | JSON to send
    try {
      AddHEwPickScnl201Response result = apiInstance.addHEwPickScnl(addHEwPickScnlRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EarthwormApiApi#addHEwPickScnl");
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
| **addHEwPickScnlRequest** | [**AddHEwPickScnlRequest**](AddHEwPickScnlRequest.md)| JSON to send | |

### Return type

[**AddHEwPickScnl201Response**](AddHEwPickScnl201Response.md)

### Authorization

No authorization required

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

<a id="addHEwStrongmotionii"></a>
# **addHEwStrongmotionii**
> AddHEwStrongmotionii201Response addHEwStrongmotionii(addHEwStrongmotioniiRequest)

Insert a new strongmotionii message to the DB using ew2openapi module

This API is used to add an Earthworm strongmotionii object.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.EarthwormApiApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    EarthwormApiApi apiInstance = new EarthwormApiApi(defaultClient);
    AddHEwStrongmotioniiRequest addHEwStrongmotioniiRequest = new AddHEwStrongmotioniiRequest(); // AddHEwStrongmotioniiRequest | JSON to send
    try {
      AddHEwStrongmotionii201Response result = apiInstance.addHEwStrongmotionii(addHEwStrongmotioniiRequest);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling EarthwormApiApi#addHEwStrongmotionii");
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
| **addHEwStrongmotioniiRequest** | [**AddHEwStrongmotioniiRequest**](AddHEwStrongmotioniiRequest.md)| JSON to send | |

### Return type

[**AddHEwStrongmotionii201Response**](AddHEwStrongmotionii201Response.md)

### Authorization

No authorization required

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

