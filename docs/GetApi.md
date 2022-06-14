# GetApi

All URIs are relative to *http://caravel.int.ingv.it/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getEvent**](GetApi.md#getEvent) | **GET** /quakedb/v1/event | This API returns the preferred origin and the preferred magnitude from all clusterd events. |
| [**getEvents**](GetApi.md#getEvents) | **GET** /quakedb/v1/events | This API returns the preferred origin and the preferred magnitude from the same instance. |
| [**getEventsPref**](GetApi.md#getEventsPref) | **GET** /quakedb/v1/events-pref | This API returns the preferred origin and the preferred magnitude from all clusterd events. |
| [**getLocalspace**](GetApi.md#getLocalspace) | **GET** /quakedb/table/v1/localspace | This API returns all the localspace(s). |
| [**getMunicipiDistanceKmPopolazione**](GetApi.md#getMunicipiDistanceKmPopolazione) | **GET** /boundaries/v1/municipi-distance-km-popolazione | This API returns the municipi-distance-km-popolazione used at INGV. |
| [**getOriginFlag**](GetApi.md#getOriginFlag) | **GET** /quakedb/v1/origin-flag | This API returns the all the flags assosiated to the originid. |
| [**getOrigins**](GetApi.md#getOrigins) | **GET** /quakedb/v1/origins | This API returns all origins and magnitudes. |
| [**getProvenance**](GetApi.md#getProvenance) | **GET** /quakedb/table/v1/provenance | This API returns all the provenance(s). |
| [**getRegionName**](GetApi.md#getRegionName) | **GET** /boundaries/v1/region-name | This API returns the region name used at INGV. |
| [**getStatus**](GetApi.md#getStatus) | **GET** /status | Return the application status |
| [**getTypeEvent**](GetApi.md#getTypeEvent) | **GET** /quakedb/table/v1/type-event | This API returns all the type_event(s). |
| [**getTypeMagnitude**](GetApi.md#getTypeMagnitude) | **GET** /quakedb/table/v1/type-magnitude | This API returns all the type_magnitude(s). |
| [**getTypeOrigin**](GetApi.md#getTypeOrigin) | **GET** /quakedb/table/v1/type-origin | This API returns all the type_origin(s). |


<a name="getEvent"></a>
# **getEvent**
> GetEvent200Response getEvent(originid, eventid, level)

This API returns the preferred origin and the preferred magnitude from all clusterd events.

This API returns the preferred origin and the preferred magnitude from all clusterd events.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    Long originid = 56L; // Long | Select by origin id.
    Long eventid = 56L; // Long | Retrieve an event based on the unique INGV event id.
    String level = "event"; // String | Select deep level
    try {
      GetEvent200Response result = apiInstance.getEvent(originid, eventid, level);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getEvent");
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
| **originid** | **Long**| Select by origin id. | [optional] |
| **eventid** | **Long**| Retrieve an event based on the unique INGV event id. | [optional] |
| **level** | **String**| Select deep level | [optional] [default to all] [enum: event, origin, magnitude, all] |

### Return type

[**GetEvent200Response**](GetEvent200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getEvents"></a>
# **getEvents**
> GetEventsPref200Response getEvents(starttime, endtime, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, orderby, eventGroupId, idLocalspace, wherelocalspacenamein, limit)

This API returns the preferred origin and the preferred magnitude from the same instance.

This API returns the preferred origin and the preferred magnitude from the same instance

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.**
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.**
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    String orderby = "event_id-asc"; // String | Select order
    Long eventGroupId = 56L; // Long | Select events with same event_group_id.
    Long idLocalspace = 56L; // Long | Localspace Id.
    String wherelocalspacenamein = "wherelocalspacenamein_example"; // String | Filter localspace.name by regex (i.e. hew10_mole,hew20_mole).
    Integer limit = 56; // Integer | Limit the results to the specified number of events.
    try {
      GetEventsPref200Response result = apiInstance.getEvents(starttime, endtime, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, orderby, eventGroupId, idLocalspace, wherelocalspacenamein, limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getEvents");
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
| **starttime** | **OffsetDateTime**| Select date start (i.e. 2016-06-22T16:52:06.260Z). | [optional] |
| **endtime** | **OffsetDateTime**| Select date end (i.e. 2016-06-22T16:52:06.260Z). | [optional] |
| **minlat** | **Double**| Specify southern boundary for search in WGS84 (i.e. 39.12). | [optional] |
| **maxlat** | **Double**| Specify northern boundary for search in WGS84 (i.e. 46.52). | [optional] |
| **minlon** | **Double**| Specify western boundary for search in WGS84 (i.e. 10.12). | [optional] |
| **maxlon** | **Double**| Specify eastern boundary for search (in WGS84) (i.e. 15.12). | [optional] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.** | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.** | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **orderby** | **String**| Select order | [optional] [enum: event_id-asc, event_id-desc, origin_ot-asc, origin_ot-desc, magnitude_mag-asc, magnitude_mag-desc] |
| **eventGroupId** | **Long**| Select events with same event_group_id. | [optional] |
| **idLocalspace** | **Long**| Localspace Id. | [optional] |
| **wherelocalspacenamein** | **String**| Filter localspace.name by regex (i.e. hew10_mole,hew20_mole). | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of events. | [optional] |

### Return type

[**GetEventsPref200Response**](GetEventsPref200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getEventsPref"></a>
# **getEventsPref**
> GetEventsPref200Response getEventsPref(starttime, endtime, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, orderby, limit)

This API returns the preferred origin and the preferred magnitude from all clusterd events.

This API returns the preferred origin and the preferred magnitude from all clusterd events.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.**
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.**
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    String orderby = "event_id-asc"; // String | Select order
    Integer limit = 56; // Integer | Limit the results to the specified number of events.
    try {
      GetEventsPref200Response result = apiInstance.getEventsPref(starttime, endtime, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, orderby, limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getEventsPref");
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
| **starttime** | **OffsetDateTime**| Select date start (i.e. 2016-06-22T16:52:06.260Z). | [optional] |
| **endtime** | **OffsetDateTime**| Select date end (i.e. 2016-06-22T16:52:06.260Z). | [optional] |
| **minlat** | **Double**| Specify southern boundary for search in WGS84 (i.e. 39.12). | [optional] |
| **maxlat** | **Double**| Specify northern boundary for search in WGS84 (i.e. 46.52). | [optional] |
| **minlon** | **Double**| Specify western boundary for search in WGS84 (i.e. 10.12). | [optional] |
| **maxlon** | **Double**| Specify eastern boundary for search (in WGS84) (i.e. 15.12). | [optional] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.** | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.** | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **orderby** | **String**| Select order | [optional] [enum: event_id-asc, event_id-desc, origin_ot-asc, origin_ot-desc, magnitude_mag-asc, magnitude_mag-desc] |
| **limit** | **Integer**| Limit the results to the specified number of events. | [optional] |

### Return type

[**GetEventsPref200Response**](GetEventsPref200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getLocalspace"></a>
# **getLocalspace**
> GetLocalspace200Response getLocalspace()

This API returns all the localspace(s).

This API returns all the localspace(s).

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    try {
      GetLocalspace200Response result = apiInstance.getLocalspace();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getLocalspace");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**GetLocalspace200Response**](GetLocalspace200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getMunicipiDistanceKmPopolazione"></a>
# **getMunicipiDistanceKmPopolazione**
> GetMunicipiDistanceKmPopolazione200Response getMunicipiDistanceKmPopolazione(mindistance, maxdistance, minpopolazione, lat, lon)

This API returns the municipi-distance-km-popolazione used at INGV.

This API returns the municipi-distance-km-popolazione.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    Double mindistance = 3.4D; // Double | Specify minimum distance (kilometers).
    Double maxdistance = 3.4D; // Double | Specify maximum distance (kilometers).
    Long minpopolazione = 56L; // Long | Specify minimum popolazione.
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    try {
      GetMunicipiDistanceKmPopolazione200Response result = apiInstance.getMunicipiDistanceKmPopolazione(mindistance, maxdistance, minpopolazione, lat, lon);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getMunicipiDistanceKmPopolazione");
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
| **mindistance** | **Double**| Specify minimum distance (kilometers). | |
| **maxdistance** | **Double**| Specify maximum distance (kilometers). | |
| **minpopolazione** | **Long**| Specify minimum popolazione. | |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |

### Return type

[**GetMunicipiDistanceKmPopolazione200Response**](GetMunicipiDistanceKmPopolazione200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getOriginFlag"></a>
# **getOriginFlag**
> GetOriginFlag200Response getOriginFlag(originid)

This API returns the all the flags assosiated to the originid.

This API returns the all the flags assosiated to the originid.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    Long originid = 56L; // Long | Select by origin id.
    try {
      GetOriginFlag200Response result = apiInstance.getOriginFlag(originid);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getOriginFlag");
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
| **originid** | **Long**| Select by origin id. | [optional] |

### Return type

[**GetOriginFlag200Response**](GetOriginFlag200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getOrigins"></a>
# **getOrigins**
> GetEventsPref200Response getOrigins(starttime, endtime, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, orderby, idLocalspace, wherelocalspacenamein, limit)

This API returns all origins and magnitudes.

This API returns all the origins and the magnitudes

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.**
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.**
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    String orderby = "event_id-asc"; // String | Select order
    Long idLocalspace = 56L; // Long | Localspace Id.
    String wherelocalspacenamein = "wherelocalspacenamein_example"; // String | Filter localspace.name by regex (i.e. hew10_mole,hew20_mole).
    Integer limit = 56; // Integer | Limit the results to the specified number of events.
    try {
      GetEventsPref200Response result = apiInstance.getOrigins(starttime, endtime, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, orderby, idLocalspace, wherelocalspacenamein, limit);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getOrigins");
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
| **starttime** | **OffsetDateTime**| Select date start (i.e. 2016-06-22T16:52:06.260Z). | [optional] |
| **endtime** | **OffsetDateTime**| Select date end (i.e. 2016-06-22T16:52:06.260Z). | [optional] |
| **minlat** | **Double**| Specify southern boundary for search in WGS84 (i.e. 39.12). | [optional] |
| **maxlat** | **Double**| Specify northern boundary for search in WGS84 (i.e. 46.52). | [optional] |
| **minlon** | **Double**| Specify western boundary for search in WGS84 (i.e. 10.12). | [optional] |
| **maxlon** | **Double**| Specify eastern boundary for search (in WGS84) (i.e. 15.12). | [optional] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.** | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. **This is an INGV extension to the FDSN specification.** | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **orderby** | **String**| Select order | [optional] [enum: event_id-asc, event_id-desc, origin_ot-asc, origin_ot-desc, magnitude_mag-asc, magnitude_mag-desc] |
| **idLocalspace** | **Long**| Localspace Id. | [optional] |
| **wherelocalspacenamein** | **String**| Filter localspace.name by regex (i.e. hew10_mole,hew20_mole). | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of events. | [optional] |

### Return type

[**GetEventsPref200Response**](GetEventsPref200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getProvenance"></a>
# **getProvenance**
> GetProvenance200Response getProvenance()

This API returns all the provenance(s).

This API returns all the provenance(s).

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    try {
      GetProvenance200Response result = apiInstance.getProvenance();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getProvenance");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**GetProvenance200Response**](GetProvenance200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getRegionName"></a>
# **getRegionName**
> GetRegionName200Response getRegionName(lat, lon)

This API returns the region name used at INGV.

This API returns the region name.

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    try {
      GetRegionName200Response result = apiInstance.getRegionName(lat, lon);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getRegionName");
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
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |

### Return type

[**GetRegionName200Response**](GetRegionName200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getStatus"></a>
# **getStatus**
> ObjectStatus getStatus()

Return the application status

Return the application status

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    try {
      ObjectStatus result = apiInstance.getStatus();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getStatus");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**ObjectStatus**](ObjectStatus.md)

### Authorization

No authorization required

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
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  * Cache-Control -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getTypeEvent"></a>
# **getTypeEvent**
> GetTypeEvent200Response getTypeEvent()

This API returns all the type_event(s).

This API returns all the type_event(s).

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    try {
      GetTypeEvent200Response result = apiInstance.getTypeEvent();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getTypeEvent");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**GetTypeEvent200Response**](GetTypeEvent200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getTypeMagnitude"></a>
# **getTypeMagnitude**
> GetTypeMagnitude200Response getTypeMagnitude()

This API returns all the type_magnitude(s).

This API returns all the type_magnitude(s).

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    try {
      GetTypeMagnitude200Response result = apiInstance.getTypeMagnitude();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getTypeMagnitude");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**GetTypeMagnitude200Response**](GetTypeMagnitude200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a name="getTypeOrigin"></a>
# **getTypeOrigin**
> GetTypeOrigin200Response getTypeOrigin()

This API returns all the type_origin(s).

This API returns all the type_origin(s).

### Example
```java
// Import classes:
import org.ingv.dante.ApiClient;
import org.ingv.dante.ApiException;
import org.ingv.dante.Configuration;
import org.ingv.dante.models.*;
import org.ingv.dante.api.GetApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://caravel.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    try {
      GetTypeOrigin200Response result = apiInstance.getTypeOrigin();
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getTypeOrigin");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**GetTypeOrigin200Response**](GetTypeOrigin200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

