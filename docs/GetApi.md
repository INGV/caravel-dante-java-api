# GetApi

All URIs are relative to *https://caravel-dante.int.ingv.it/api*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getAll**](GetApi.md#getAll) | **GET** /quakedb/v1/all | This API returns all origins with all magnitude; one per line. |
| [**getEvent**](GetApi.md#getEvent) | **GET** /quakedb/v1/event | This API returns the preferred origin and the preferred magnitude from all clusterd events. |
| [**getEvents**](GetApi.md#getEvents) | **GET** /quakedb/v1/events | This API returns the preferred origin and the preferred magnitude from the same instance. |
| [**getEventsCatalog**](GetApi.md#getEventsCatalog) | **GET** /quakedb/v1/events-catalog | This API returns the catalogs. |
| [**getEventsGroup**](GetApi.md#getEventsGroup) | **GET** /quakedb/v1/events-group | This API returns the preferred origin and the preferred magnitude from all clusterd events. |
| [**getLocalspace**](GetApi.md#getLocalspace) | **GET** /quakedb/table/v1/localspace | This API returns all the localspace(s). |
| [**getMagnitudes**](GetApi.md#getMagnitudes) | **GET** /quakedb/v1/magnitudes | This API returns all origins with own preferred magnitude. |
| [**getMunicipiDistanceKmPopolazione**](GetApi.md#getMunicipiDistanceKmPopolazione) | **GET** /boundaries/v1/municipi-distance-km-popolazione | This API returns the municipi-distance-km-popolazione used at INGV. |
| [**getMunicipio**](GetApi.md#getMunicipio) | **GET** /boundaries/v1/municipio | This API returns the Italian \&quot;municipio\&quot; information by name. |
| [**getOriginFlag**](GetApi.md#getOriginFlag) | **GET** /quakedb/v1/origin-flag | This API returns the all the flags assosiated to the originid. |
| [**getOrigins**](GetApi.md#getOrigins) | **GET** /quakedb/v1/origins | This API returns all the preferred origins. |
| [**getPick**](GetApi.md#getPick) | **GET** /quakedb/v1/pick | This API returns picks from DataBase |
| [**getProvenance**](GetApi.md#getProvenance) | **GET** /quakedb/table/v1/provenance | This API returns all the provenance(s). |
| [**getRegionName**](GetApi.md#getRegionName) | **GET** /boundaries/v1/region-name | This API returns the region name used at INGV. |
| [**getScnl**](GetApi.md#getScnl) | **GET** /quakedb/v1/scnl | This API returns scnls from DataBase |
| [**getTypeEvent**](GetApi.md#getTypeEvent) | **GET** /quakedb/table/v1/type-event | This API returns all the type_event(s). |
| [**getTypeMagnitude**](GetApi.md#getTypeMagnitude) | **GET** /quakedb/table/v1/type-magnitude | This API returns all the type_magnitude(s). |
| [**getTypeOrigin**](GetApi.md#getTypeOrigin) | **GET** /quakedb/table/v1/type-origin | This API returns all the type_origin(s). |


<a id="getAll"></a>
# **getAll**
> GetEventsGroup200Response getAll(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid)

This API returns all origins with all magnitude; one per line.

This API returns all the origins with all magnitudes; one per line

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    String orpolygon = "orpolygon_example"; // String | Specify a list of polygons to select data.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `orpolygon=12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3`.
    String notinpolygon = "notinpolygon_example"; // String | Specify a list of polygons to NOT select data within.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `notinpolygon=12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8`
    List<String> wherepolygonnamein = Arrays.asList(); // List<String> | Specify a list of pre-set polygons.   Each poligon is `,` separated value.  * Example: `wherepolygonnamein=area_confine_italia,area_vulcanica_italia`
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    Integer minnphtot = 56; // Integer | Specify minimum number of phases (P&S) with weight > 0.0.
    Double mindistance = 3.4D; // Double | Specify minimum distance from the closest station (kilometers).
    List<String> wheretypeeventnamein = Arrays.asList(); // List<String> | Filter by \"event.type_event\" by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> wheretypeeventnamenotin = Arrays.asList(); // List<String> | Filter by \"event.type_event\" - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> whereoriginqualityin = Arrays.asList(); // List<String> | Filter by \"origin.quality\" by comma separated value (i.e. AA,AB,BC).
    List<String> wheremagnitudemagqualityin = Arrays.asList(); // List<String> | Filter by \"magnitude.mag_quality\" by comma separated value (i.e. A,B,BC,DD).
    Long mintypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 0).
    Long maxtypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 1000).
    Boolean origindirectlinktoevent = false; // Boolean | Origin entity is directly linked to Event entity (`origin.fk_event=event.id`)
    Boolean magnitudedirectlinktoorigin = false; // Boolean | Magnitude entity is directly linked to Origin entity (`magnitude.fk_origin=origin.id`)
    Boolean magnitudedirectlinktoevent = false; // Boolean | Magnitude entity is directly linked to Event entity `(magnitude.fk_origin=origin.id AND origin.fk_event=event.id`)
    String wheretypeoriginvaluein = "wheretypeoriginvaluein_example"; // String | Filter by type_origin.version_value (i.e. 0,1,200).
    String wheretypemagnitudenameregexp = "wheretypemagnitudenameregexp_example"; // String | Filter by type_magnitude.name using case-insensitive regexp (i.e. \"^ml.\\*\" or \"^ml.*|^mwp$\").
    List<String> whereeventlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"event.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereoriginlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> whereoriginlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"origin.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> wheremagnitudelocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"magnitude.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"whereoriginlocalspaceenvironmentin\".
    String whereeventlocalspacenamein = "whereeventlocalspacenamein_example"; // String | Filter by \"event.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereoriginlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String whereoriginlocalspacenamein = "whereoriginlocalspacenamein_example"; // String | Filter by \"origin.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String wheremagnitudelocalspacenamein = "wheremagnitudelocalspacenamein_example"; // String | Filter by \"magnitude.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"whereoriginlocalspacenamein\".
    OffsetDateTime eventupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"event.modified\" after; if \"originupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime originupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"origin.modified\" after; if \"eventupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime magnitudeupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"magnitude.modified\" after; if \"eventupdatedafter\" and/or \"originupdatedafter\" are set, the \"updatedafteroperator\" is used.
    String updatedafteroperator = "and"; // String | Set the \"operator\" to use when \"eventupdatedafter\", \"originupdatedafter\" and \"magnitudeupdatedafter\" are set.
    String whereflagsin = "whereflagsin_example"; // String | Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \"OR\".
    String orderby = "orderby_example"; // String | Select \"order by\"; multiple \"order\" contatenation available (i.e. event_id-desc,type_origin_version_value-asc)
    Long eventGroupId = 56L; // Long | Select events with same event_group_id.
    Long idLocalspace = 56L; // Long | Localspace Id.
    Integer limit = 56; // Integer | Limit the results to the specified number of records.
    Integer page = 56; // Integer | Pagination.
    Long eventid = 56L; // Long | Select by event id.
    Long originid = 56L; // Long | Select by origin id.
    Long magnitudeid = 56L; // Long | Select by magnitude id.
    try {
      GetEventsGroup200Response result = apiInstance.getAll(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getAll");
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
| **orpolygon** | **String**| Specify a list of polygons to select data.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;orpolygon&#x3D;12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3&#x60;. | [optional] |
| **notinpolygon** | **String**| Specify a list of polygons to NOT select data within.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;notinpolygon&#x3D;12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8&#x60; | [optional] |
| **wherepolygonnamein** | [**List&lt;String&gt;**](String.md)| Specify a list of pre-set polygons.   Each poligon is &#x60;,&#x60; separated value.  * Example: &#x60;wherepolygonnamein&#x3D;area_confine_italia,area_vulcanica_italia&#x60; | [optional] [enum: settore_1_pol, settore_2_pol, settore_cat_pol, aree_vulcaniche_italia_2020, ov_aree_vulcani_mari, area_vulcanica_italia, area_confine_italia] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **minnphtot** | **Integer**| Specify minimum number of phases (P&amp;S) with weight &gt; 0.0. | [optional] |
| **mindistance** | **Double**| Specify minimum distance from the closest station (kilometers). | [optional] |
| **wheretypeeventnamein** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **wheretypeeventnamenotin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **whereoriginqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.quality\&quot; by comma separated value (i.e. AA,AB,BC). | [optional] [enum: AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **wheremagnitudemagqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.mag_quality\&quot; by comma separated value (i.e. A,B,BC,DD). | [optional] [enum: A, B, C, D, AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **mintypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 0). | [optional] |
| **maxtypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 1000). | [optional] |
| **origindirectlinktoevent** | **Boolean**| Origin entity is directly linked to Event entity (&#x60;origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoorigin** | **Boolean**| Magnitude entity is directly linked to Origin entity (&#x60;magnitude.fk_origin&#x3D;origin.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoevent** | **Boolean**| Magnitude entity is directly linked to Event entity &#x60;(magnitude.fk_origin&#x3D;origin.id AND origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **wheretypeoriginvaluein** | **String**| Filter by type_origin.version_value (i.e. 0,1,200). | [optional] |
| **wheretypemagnitudenameregexp** | **String**| Filter by type_magnitude.name using case-insensitive regexp (i.e. \&quot;^ml.\\*\&quot; or \&quot;^ml.*|^mwp$\&quot;). | [optional] |
| **whereeventlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereoriginlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **wheremagnitudelocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;whereoriginlocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereeventlocalspacenamein** | **String**| Filter by \&quot;event.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **whereoriginlocalspacenamein** | **String**| Filter by \&quot;origin.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **wheremagnitudelocalspacenamein** | **String**| Filter by \&quot;magnitude.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;whereoriginlocalspacenamein\&quot;. | [optional] |
| **eventupdatedafter** | **OffsetDateTime**| Limit data to \&quot;event.modified\&quot; after; if \&quot;originupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **originupdatedafter** | **OffsetDateTime**| Limit data to \&quot;origin.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **magnitudeupdatedafter** | **OffsetDateTime**| Limit data to \&quot;magnitude.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;originupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **updatedafteroperator** | **String**| Set the \&quot;operator\&quot; to use when \&quot;eventupdatedafter\&quot;, \&quot;originupdatedafter\&quot; and \&quot;magnitudeupdatedafter\&quot; are set. | [optional] [default to or] [enum: and, or] |
| **whereflagsin** | **String**| Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \&quot;OR\&quot;. | [optional] |
| **orderby** | **String**| Select \&quot;order by\&quot;; multiple \&quot;order\&quot; contatenation available (i.e. event_id-desc,type_origin_version_value-asc) | [optional] |
| **eventGroupId** | **Long**| Select events with same event_group_id. | [optional] |
| **idLocalspace** | **Long**| Localspace Id. | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of records. | [optional] |
| **page** | **Integer**| Pagination. | [optional] |
| **eventid** | **Long**| Select by event id. | [optional] |
| **originid** | **Long**| Select by origin id. | [optional] |
| **magnitudeid** | **Long**| Select by magnitude id. | [optional] |

### Return type

[**GetEventsGroup200Response**](GetEventsGroup200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getEvent"></a>
# **getEvent**
> GetEvent200Response getEvent(originid, eventid, level, originOrderby, magnitudeOrderby)

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    Long originid = 56L; // Long | Select by origin id.
    Long eventid = 56L; // Long | Select by event id.
    String level = "event"; // String | Select deep level
    String originOrderby = "type_origin_version_value-asc"; // String | Select origins \"order by\"
    String magnitudeOrderby = "type_magnitude_priority-asc"; // String | Select magnitudes \"order by\"
    try {
      GetEvent200Response result = apiInstance.getEvent(originid, eventid, level, originOrderby, magnitudeOrderby);
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
| **eventid** | **Long**| Select by event id. | [optional] |
| **level** | **String**| Select deep level | [optional] [default to all] [enum: event, origin, magnitude, all] |
| **originOrderby** | **String**| Select origins \&quot;order by\&quot; | [optional] [default to type_origin_priority-asc] [enum: type_origin_version_value-asc, type_origin_version_value-desc, type_origin_priority-asc, type_origin_priority-desc] |
| **magnitudeOrderby** | **String**| Select magnitudes \&quot;order by\&quot; | [optional] [default to type_magnitude_priority-asc] [enum: type_magnitude_priority-asc, type_magnitude_priority-desc] |

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getEvents"></a>
# **getEvents**
> GetEventsGroup200Response getEvents(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid)

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    String orpolygon = "orpolygon_example"; // String | Specify a list of polygons to select data.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `orpolygon=12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3`.
    String notinpolygon = "notinpolygon_example"; // String | Specify a list of polygons to NOT select data within.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `notinpolygon=12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8`
    List<String> wherepolygonnamein = Arrays.asList(); // List<String> | Specify a list of pre-set polygons.   Each poligon is `,` separated value.  * Example: `wherepolygonnamein=area_confine_italia,area_vulcanica_italia`
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    Integer minnphtot = 56; // Integer | Specify minimum number of phases (P&S) with weight > 0.0.
    Double mindistance = 3.4D; // Double | Specify minimum distance from the closest station (kilometers).
    List<String> wheretypeeventnamein = Arrays.asList(); // List<String> | Filter by \"event.type_event\" by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> wheretypeeventnamenotin = Arrays.asList(); // List<String> | Filter by \"event.type_event\" - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> whereoriginqualityin = Arrays.asList(); // List<String> | Filter by \"origin.quality\" by comma separated value (i.e. AA,AB,BC).
    List<String> wheremagnitudemagqualityin = Arrays.asList(); // List<String> | Filter by \"magnitude.mag_quality\" by comma separated value (i.e. A,B,BC,DD).
    Long mintypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 0).
    Long maxtypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 1000).
    Boolean origindirectlinktoevent = false; // Boolean | Origin entity is directly linked to Event entity (`origin.fk_event=event.id`)
    Boolean magnitudedirectlinktoorigin = false; // Boolean | Magnitude entity is directly linked to Origin entity (`magnitude.fk_origin=origin.id`)
    Boolean magnitudedirectlinktoevent = false; // Boolean | Magnitude entity is directly linked to Event entity `(magnitude.fk_origin=origin.id AND origin.fk_event=event.id`)
    String wheretypeoriginvaluein = "wheretypeoriginvaluein_example"; // String | Filter by type_origin.version_value (i.e. 0,1,200).
    String wheretypemagnitudenameregexp = "wheretypemagnitudenameregexp_example"; // String | Filter by type_magnitude.name using case-insensitive regexp (i.e. \"^ml.\\*\" or \"^ml.*|^mwp$\").
    List<String> whereeventlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"event.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereoriginlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> whereoriginlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"origin.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> wheremagnitudelocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"magnitude.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"whereoriginlocalspaceenvironmentin\".
    String whereeventlocalspacenamein = "whereeventlocalspacenamein_example"; // String | Filter by \"event.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereoriginlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String whereoriginlocalspacenamein = "whereoriginlocalspacenamein_example"; // String | Filter by \"origin.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String wheremagnitudelocalspacenamein = "wheremagnitudelocalspacenamein_example"; // String | Filter by \"magnitude.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"whereoriginlocalspacenamein\".
    OffsetDateTime eventupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"event.modified\" after; if \"originupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime originupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"origin.modified\" after; if \"eventupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime magnitudeupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"magnitude.modified\" after; if \"eventupdatedafter\" and/or \"originupdatedafter\" are set, the \"updatedafteroperator\" is used.
    String updatedafteroperator = "and"; // String | Set the \"operator\" to use when \"eventupdatedafter\", \"originupdatedafter\" and \"magnitudeupdatedafter\" are set.
    String whereflagsin = "whereflagsin_example"; // String | Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \"OR\".
    String orderby = "orderby_example"; // String | Select \"order by\"; multiple \"order\" contatenation available (i.e. event_id-desc,type_origin_version_value-asc)
    Long eventGroupId = 56L; // Long | Select events with same event_group_id.
    Long idLocalspace = 56L; // Long | Localspace Id.
    Integer limit = 56; // Integer | Limit the results to the specified number of records.
    Integer page = 56; // Integer | Pagination.
    Long eventid = 56L; // Long | Select by event id.
    Long originid = 56L; // Long | Select by origin id.
    Long magnitudeid = 56L; // Long | Select by magnitude id.
    try {
      GetEventsGroup200Response result = apiInstance.getEvents(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid);
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
| **orpolygon** | **String**| Specify a list of polygons to select data.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;orpolygon&#x3D;12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3&#x60;. | [optional] |
| **notinpolygon** | **String**| Specify a list of polygons to NOT select data within.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;notinpolygon&#x3D;12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8&#x60; | [optional] |
| **wherepolygonnamein** | [**List&lt;String&gt;**](String.md)| Specify a list of pre-set polygons.   Each poligon is &#x60;,&#x60; separated value.  * Example: &#x60;wherepolygonnamein&#x3D;area_confine_italia,area_vulcanica_italia&#x60; | [optional] [enum: settore_1_pol, settore_2_pol, settore_cat_pol, aree_vulcaniche_italia_2020, ov_aree_vulcani_mari, area_vulcanica_italia, area_confine_italia] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **minnphtot** | **Integer**| Specify minimum number of phases (P&amp;S) with weight &gt; 0.0. | [optional] |
| **mindistance** | **Double**| Specify minimum distance from the closest station (kilometers). | [optional] |
| **wheretypeeventnamein** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **wheretypeeventnamenotin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **whereoriginqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.quality\&quot; by comma separated value (i.e. AA,AB,BC). | [optional] [enum: AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **wheremagnitudemagqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.mag_quality\&quot; by comma separated value (i.e. A,B,BC,DD). | [optional] [enum: A, B, C, D, AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **mintypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 0). | [optional] |
| **maxtypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 1000). | [optional] |
| **origindirectlinktoevent** | **Boolean**| Origin entity is directly linked to Event entity (&#x60;origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoorigin** | **Boolean**| Magnitude entity is directly linked to Origin entity (&#x60;magnitude.fk_origin&#x3D;origin.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoevent** | **Boolean**| Magnitude entity is directly linked to Event entity &#x60;(magnitude.fk_origin&#x3D;origin.id AND origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **wheretypeoriginvaluein** | **String**| Filter by type_origin.version_value (i.e. 0,1,200). | [optional] |
| **wheretypemagnitudenameregexp** | **String**| Filter by type_magnitude.name using case-insensitive regexp (i.e. \&quot;^ml.\\*\&quot; or \&quot;^ml.*|^mwp$\&quot;). | [optional] |
| **whereeventlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereoriginlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **wheremagnitudelocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;whereoriginlocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereeventlocalspacenamein** | **String**| Filter by \&quot;event.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **whereoriginlocalspacenamein** | **String**| Filter by \&quot;origin.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **wheremagnitudelocalspacenamein** | **String**| Filter by \&quot;magnitude.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;whereoriginlocalspacenamein\&quot;. | [optional] |
| **eventupdatedafter** | **OffsetDateTime**| Limit data to \&quot;event.modified\&quot; after; if \&quot;originupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **originupdatedafter** | **OffsetDateTime**| Limit data to \&quot;origin.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **magnitudeupdatedafter** | **OffsetDateTime**| Limit data to \&quot;magnitude.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;originupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **updatedafteroperator** | **String**| Set the \&quot;operator\&quot; to use when \&quot;eventupdatedafter\&quot;, \&quot;originupdatedafter\&quot; and \&quot;magnitudeupdatedafter\&quot; are set. | [optional] [default to or] [enum: and, or] |
| **whereflagsin** | **String**| Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \&quot;OR\&quot;. | [optional] |
| **orderby** | **String**| Select \&quot;order by\&quot;; multiple \&quot;order\&quot; contatenation available (i.e. event_id-desc,type_origin_version_value-asc) | [optional] |
| **eventGroupId** | **Long**| Select events with same event_group_id. | [optional] |
| **idLocalspace** | **Long**| Localspace Id. | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of records. | [optional] |
| **page** | **Integer**| Pagination. | [optional] |
| **eventid** | **Long**| Select by event id. | [optional] |
| **originid** | **Long**| Select by origin id. | [optional] |
| **magnitudeid** | **Long**| Select by magnitude id. | [optional] |

### Return type

[**GetEventsGroup200Response**](GetEventsGroup200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getEventsCatalog"></a>
# **getEventsCatalog**
> GetEventsCatalog200Response getEventsCatalog(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid, doi)

This API returns the catalogs.

This API returns only the \&quot;catalogs\&quot;.   All &#x60;catalogs&#x60; are identified by &#x60;event.localspace.environment&#x3D;catalog&#x60; and the name of catalog is &#x60;event.localspace.name&#x60;.    To search a specific catalog, use &#x60;whereeventlocalspacenamein&#x60; parameter and/or &#x60;doi&#x60; paramenter.

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    String orpolygon = "orpolygon_example"; // String | Specify a list of polygons to select data.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `orpolygon=12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3`.
    String notinpolygon = "notinpolygon_example"; // String | Specify a list of polygons to NOT select data within.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `notinpolygon=12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8`
    List<String> wherepolygonnamein = Arrays.asList(); // List<String> | Specify a list of pre-set polygons.   Each poligon is `,` separated value.  * Example: `wherepolygonnamein=area_confine_italia,area_vulcanica_italia`
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    Integer minnphtot = 56; // Integer | Specify minimum number of phases (P&S) with weight > 0.0.
    Double mindistance = 3.4D; // Double | Specify minimum distance from the closest station (kilometers).
    List<String> wheretypeeventnamein = Arrays.asList(); // List<String> | Filter by \"event.type_event\" by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> wheretypeeventnamenotin = Arrays.asList(); // List<String> | Filter by \"event.type_event\" - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> whereoriginqualityin = Arrays.asList(); // List<String> | Filter by \"origin.quality\" by comma separated value (i.e. AA,AB,BC).
    List<String> wheremagnitudemagqualityin = Arrays.asList(); // List<String> | Filter by \"magnitude.mag_quality\" by comma separated value (i.e. A,B,BC,DD).
    Long mintypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 0).
    Long maxtypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 1000).
    Boolean origindirectlinktoevent = false; // Boolean | Origin entity is directly linked to Event entity (`origin.fk_event=event.id`)
    Boolean magnitudedirectlinktoorigin = false; // Boolean | Magnitude entity is directly linked to Origin entity (`magnitude.fk_origin=origin.id`)
    Boolean magnitudedirectlinktoevent = false; // Boolean | Magnitude entity is directly linked to Event entity `(magnitude.fk_origin=origin.id AND origin.fk_event=event.id`)
    String wheretypeoriginvaluein = "wheretypeoriginvaluein_example"; // String | Filter by type_origin.version_value (i.e. 0,1,200).
    String wheretypemagnitudenameregexp = "wheretypemagnitudenameregexp_example"; // String | Filter by type_magnitude.name using case-insensitive regexp (i.e. \"^ml.\\*\" or \"^ml.*|^mwp$\").
    List<String> whereeventlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"event.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereoriginlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> whereoriginlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"origin.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> wheremagnitudelocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"magnitude.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"whereoriginlocalspaceenvironmentin\".
    String whereeventlocalspacenamein = "whereeventlocalspacenamein_example"; // String | Filter by \"event.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereoriginlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String whereoriginlocalspacenamein = "whereoriginlocalspacenamein_example"; // String | Filter by \"origin.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String wheremagnitudelocalspacenamein = "wheremagnitudelocalspacenamein_example"; // String | Filter by \"magnitude.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"whereoriginlocalspacenamein\".
    OffsetDateTime eventupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"event.modified\" after; if \"originupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime originupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"origin.modified\" after; if \"eventupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime magnitudeupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"magnitude.modified\" after; if \"eventupdatedafter\" and/or \"originupdatedafter\" are set, the \"updatedafteroperator\" is used.
    String updatedafteroperator = "and"; // String | Set the \"operator\" to use when \"eventupdatedafter\", \"originupdatedafter\" and \"magnitudeupdatedafter\" are set.
    String whereflagsin = "whereflagsin_example"; // String | Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \"OR\".
    String orderby = "orderby_example"; // String | Select \"order by\"; multiple \"order\" contatenation available (i.e. event_id-desc,type_origin_version_value-asc)
    Long eventGroupId = 56L; // Long | Select events with same event_group_id.
    Long idLocalspace = 56L; // Long | Localspace Id.
    Integer limit = 56; // Integer | Limit the results to the specified number of records.
    Integer page = 56; // Integer | Pagination.
    Long eventid = 56L; // Long | Select by event id.
    Long originid = 56L; // Long | Select by origin id.
    Long magnitudeid = 56L; // Long | Select by magnitude id.
    String doi = "doi_example"; // String | Doi.
    try {
      GetEventsCatalog200Response result = apiInstance.getEventsCatalog(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid, doi);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getEventsCatalog");
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
| **orpolygon** | **String**| Specify a list of polygons to select data.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;orpolygon&#x3D;12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3&#x60;. | [optional] |
| **notinpolygon** | **String**| Specify a list of polygons to NOT select data within.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;notinpolygon&#x3D;12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8&#x60; | [optional] |
| **wherepolygonnamein** | [**List&lt;String&gt;**](String.md)| Specify a list of pre-set polygons.   Each poligon is &#x60;,&#x60; separated value.  * Example: &#x60;wherepolygonnamein&#x3D;area_confine_italia,area_vulcanica_italia&#x60; | [optional] [enum: settore_1_pol, settore_2_pol, settore_cat_pol, aree_vulcaniche_italia_2020, ov_aree_vulcani_mari, area_vulcanica_italia, area_confine_italia] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **minnphtot** | **Integer**| Specify minimum number of phases (P&amp;S) with weight &gt; 0.0. | [optional] |
| **mindistance** | **Double**| Specify minimum distance from the closest station (kilometers). | [optional] |
| **wheretypeeventnamein** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **wheretypeeventnamenotin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **whereoriginqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.quality\&quot; by comma separated value (i.e. AA,AB,BC). | [optional] [enum: AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **wheremagnitudemagqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.mag_quality\&quot; by comma separated value (i.e. A,B,BC,DD). | [optional] [enum: A, B, C, D, AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **mintypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 0). | [optional] |
| **maxtypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 1000). | [optional] |
| **origindirectlinktoevent** | **Boolean**| Origin entity is directly linked to Event entity (&#x60;origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoorigin** | **Boolean**| Magnitude entity is directly linked to Origin entity (&#x60;magnitude.fk_origin&#x3D;origin.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoevent** | **Boolean**| Magnitude entity is directly linked to Event entity &#x60;(magnitude.fk_origin&#x3D;origin.id AND origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **wheretypeoriginvaluein** | **String**| Filter by type_origin.version_value (i.e. 0,1,200). | [optional] |
| **wheretypemagnitudenameregexp** | **String**| Filter by type_magnitude.name using case-insensitive regexp (i.e. \&quot;^ml.\\*\&quot; or \&quot;^ml.*|^mwp$\&quot;). | [optional] |
| **whereeventlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereoriginlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **wheremagnitudelocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;whereoriginlocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereeventlocalspacenamein** | **String**| Filter by \&quot;event.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **whereoriginlocalspacenamein** | **String**| Filter by \&quot;origin.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **wheremagnitudelocalspacenamein** | **String**| Filter by \&quot;magnitude.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;whereoriginlocalspacenamein\&quot;. | [optional] |
| **eventupdatedafter** | **OffsetDateTime**| Limit data to \&quot;event.modified\&quot; after; if \&quot;originupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **originupdatedafter** | **OffsetDateTime**| Limit data to \&quot;origin.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **magnitudeupdatedafter** | **OffsetDateTime**| Limit data to \&quot;magnitude.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;originupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **updatedafteroperator** | **String**| Set the \&quot;operator\&quot; to use when \&quot;eventupdatedafter\&quot;, \&quot;originupdatedafter\&quot; and \&quot;magnitudeupdatedafter\&quot; are set. | [optional] [default to or] [enum: and, or] |
| **whereflagsin** | **String**| Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \&quot;OR\&quot;. | [optional] |
| **orderby** | **String**| Select \&quot;order by\&quot;; multiple \&quot;order\&quot; contatenation available (i.e. event_id-desc,type_origin_version_value-asc) | [optional] |
| **eventGroupId** | **Long**| Select events with same event_group_id. | [optional] |
| **idLocalspace** | **Long**| Localspace Id. | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of records. | [optional] |
| **page** | **Integer**| Pagination. | [optional] |
| **eventid** | **Long**| Select by event id. | [optional] |
| **originid** | **Long**| Select by origin id. | [optional] |
| **magnitudeid** | **Long**| Select by magnitude id. | [optional] |
| **doi** | **String**| Doi. | [optional] |

### Return type

[**GetEventsCatalog200Response**](GetEventsCatalog200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getEventsGroup"></a>
# **getEventsGroup**
> GetEventsGroup200Response getEventsGroup(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid)

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    String orpolygon = "orpolygon_example"; // String | Specify a list of polygons to select data.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `orpolygon=12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3`.
    String notinpolygon = "notinpolygon_example"; // String | Specify a list of polygons to NOT select data within.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `notinpolygon=12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8`
    List<String> wherepolygonnamein = Arrays.asList(); // List<String> | Specify a list of pre-set polygons.   Each poligon is `,` separated value.  * Example: `wherepolygonnamein=area_confine_italia,area_vulcanica_italia`
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    Integer minnphtot = 56; // Integer | Specify minimum number of phases (P&S) with weight > 0.0.
    Double mindistance = 3.4D; // Double | Specify minimum distance from the closest station (kilometers).
    List<String> wheretypeeventnamein = Arrays.asList(); // List<String> | Filter by \"event.type_event\" by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> wheretypeeventnamenotin = Arrays.asList(); // List<String> | Filter by \"event.type_event\" - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> whereoriginqualityin = Arrays.asList(); // List<String> | Filter by \"origin.quality\" by comma separated value (i.e. AA,AB,BC).
    List<String> wheremagnitudemagqualityin = Arrays.asList(); // List<String> | Filter by \"magnitude.mag_quality\" by comma separated value (i.e. A,B,BC,DD).
    Long mintypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 0).
    Long maxtypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 1000).
    Boolean origindirectlinktoevent = false; // Boolean | Origin entity is directly linked to Event entity (`origin.fk_event=event.id`)
    Boolean magnitudedirectlinktoorigin = false; // Boolean | Magnitude entity is directly linked to Origin entity (`magnitude.fk_origin=origin.id`)
    Boolean magnitudedirectlinktoevent = false; // Boolean | Magnitude entity is directly linked to Event entity `(magnitude.fk_origin=origin.id AND origin.fk_event=event.id`)
    String wheretypeoriginvaluein = "wheretypeoriginvaluein_example"; // String | Filter by type_origin.version_value (i.e. 0,1,200).
    String wheretypemagnitudenameregexp = "wheretypemagnitudenameregexp_example"; // String | Filter by type_magnitude.name using case-insensitive regexp (i.e. \"^ml.\\*\" or \"^ml.*|^mwp$\").
    List<String> whereeventlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"event.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereoriginlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> whereoriginlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"origin.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> wheremagnitudelocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"magnitude.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"whereoriginlocalspaceenvironmentin\".
    String whereeventlocalspacenamein = "whereeventlocalspacenamein_example"; // String | Filter by \"event.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereoriginlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String whereoriginlocalspacenamein = "whereoriginlocalspacenamein_example"; // String | Filter by \"origin.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String wheremagnitudelocalspacenamein = "wheremagnitudelocalspacenamein_example"; // String | Filter by \"magnitude.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"whereoriginlocalspacenamein\".
    OffsetDateTime eventupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"event.modified\" after; if \"originupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime originupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"origin.modified\" after; if \"eventupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime magnitudeupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"magnitude.modified\" after; if \"eventupdatedafter\" and/or \"originupdatedafter\" are set, the \"updatedafteroperator\" is used.
    String updatedafteroperator = "and"; // String | Set the \"operator\" to use when \"eventupdatedafter\", \"originupdatedafter\" and \"magnitudeupdatedafter\" are set.
    String whereflagsin = "whereflagsin_example"; // String | Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \"OR\".
    String orderby = "orderby_example"; // String | Select \"order by\"; multiple \"order\" contatenation available (i.e. event_id-desc,type_origin_version_value-asc)
    Long eventGroupId = 56L; // Long | Select events with same event_group_id.
    Long idLocalspace = 56L; // Long | Localspace Id.
    Integer limit = 56; // Integer | Limit the results to the specified number of records.
    Integer page = 56; // Integer | Pagination.
    Long eventid = 56L; // Long | Select by event id.
    Long originid = 56L; // Long | Select by origin id.
    Long magnitudeid = 56L; // Long | Select by magnitude id.
    try {
      GetEventsGroup200Response result = apiInstance.getEventsGroup(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getEventsGroup");
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
| **orpolygon** | **String**| Specify a list of polygons to select data.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;orpolygon&#x3D;12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3&#x60;. | [optional] |
| **notinpolygon** | **String**| Specify a list of polygons to NOT select data within.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;notinpolygon&#x3D;12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8&#x60; | [optional] |
| **wherepolygonnamein** | [**List&lt;String&gt;**](String.md)| Specify a list of pre-set polygons.   Each poligon is &#x60;,&#x60; separated value.  * Example: &#x60;wherepolygonnamein&#x3D;area_confine_italia,area_vulcanica_italia&#x60; | [optional] [enum: settore_1_pol, settore_2_pol, settore_cat_pol, aree_vulcaniche_italia_2020, ov_aree_vulcani_mari, area_vulcanica_italia, area_confine_italia] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **minnphtot** | **Integer**| Specify minimum number of phases (P&amp;S) with weight &gt; 0.0. | [optional] |
| **mindistance** | **Double**| Specify minimum distance from the closest station (kilometers). | [optional] |
| **wheretypeeventnamein** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **wheretypeeventnamenotin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **whereoriginqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.quality\&quot; by comma separated value (i.e. AA,AB,BC). | [optional] [enum: AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **wheremagnitudemagqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.mag_quality\&quot; by comma separated value (i.e. A,B,BC,DD). | [optional] [enum: A, B, C, D, AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **mintypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 0). | [optional] |
| **maxtypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 1000). | [optional] |
| **origindirectlinktoevent** | **Boolean**| Origin entity is directly linked to Event entity (&#x60;origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoorigin** | **Boolean**| Magnitude entity is directly linked to Origin entity (&#x60;magnitude.fk_origin&#x3D;origin.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoevent** | **Boolean**| Magnitude entity is directly linked to Event entity &#x60;(magnitude.fk_origin&#x3D;origin.id AND origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **wheretypeoriginvaluein** | **String**| Filter by type_origin.version_value (i.e. 0,1,200). | [optional] |
| **wheretypemagnitudenameregexp** | **String**| Filter by type_magnitude.name using case-insensitive regexp (i.e. \&quot;^ml.\\*\&quot; or \&quot;^ml.*|^mwp$\&quot;). | [optional] |
| **whereeventlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereoriginlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **wheremagnitudelocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;whereoriginlocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereeventlocalspacenamein** | **String**| Filter by \&quot;event.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **whereoriginlocalspacenamein** | **String**| Filter by \&quot;origin.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **wheremagnitudelocalspacenamein** | **String**| Filter by \&quot;magnitude.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;whereoriginlocalspacenamein\&quot;. | [optional] |
| **eventupdatedafter** | **OffsetDateTime**| Limit data to \&quot;event.modified\&quot; after; if \&quot;originupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **originupdatedafter** | **OffsetDateTime**| Limit data to \&quot;origin.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **magnitudeupdatedafter** | **OffsetDateTime**| Limit data to \&quot;magnitude.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;originupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **updatedafteroperator** | **String**| Set the \&quot;operator\&quot; to use when \&quot;eventupdatedafter\&quot;, \&quot;originupdatedafter\&quot; and \&quot;magnitudeupdatedafter\&quot; are set. | [optional] [default to or] [enum: and, or] |
| **whereflagsin** | **String**| Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \&quot;OR\&quot;. | [optional] |
| **orderby** | **String**| Select \&quot;order by\&quot;; multiple \&quot;order\&quot; contatenation available (i.e. event_id-desc,type_origin_version_value-asc) | [optional] |
| **eventGroupId** | **Long**| Select events with same event_group_id. | [optional] |
| **idLocalspace** | **Long**| Localspace Id. | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of records. | [optional] |
| **page** | **Integer**| Pagination. | [optional] |
| **eventid** | **Long**| Select by event id. | [optional] |
| **originid** | **Long**| Select by origin id. | [optional] |
| **magnitudeid** | **Long**| Select by magnitude id. | [optional] |

### Return type

[**GetEventsGroup200Response**](GetEventsGroup200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getLocalspace"></a>
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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getMagnitudes"></a>
# **getMagnitudes**
> GetEventsGroup200Response getMagnitudes(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid)

This API returns all origins with own preferred magnitude.

This API returns all the origins with own preferred magnitude

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    String orpolygon = "orpolygon_example"; // String | Specify a list of polygons to select data.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `orpolygon=12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3`.
    String notinpolygon = "notinpolygon_example"; // String | Specify a list of polygons to NOT select data within.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `notinpolygon=12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8`
    List<String> wherepolygonnamein = Arrays.asList(); // List<String> | Specify a list of pre-set polygons.   Each poligon is `,` separated value.  * Example: `wherepolygonnamein=area_confine_italia,area_vulcanica_italia`
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    Integer minnphtot = 56; // Integer | Specify minimum number of phases (P&S) with weight > 0.0.
    Double mindistance = 3.4D; // Double | Specify minimum distance from the closest station (kilometers).
    List<String> wheretypeeventnamein = Arrays.asList(); // List<String> | Filter by \"event.type_event\" by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> wheretypeeventnamenotin = Arrays.asList(); // List<String> | Filter by \"event.type_event\" - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> whereoriginqualityin = Arrays.asList(); // List<String> | Filter by \"origin.quality\" by comma separated value (i.e. AA,AB,BC).
    List<String> wheremagnitudemagqualityin = Arrays.asList(); // List<String> | Filter by \"magnitude.mag_quality\" by comma separated value (i.e. A,B,BC,DD).
    Long mintypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 0).
    Long maxtypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 1000).
    Boolean origindirectlinktoevent = false; // Boolean | Origin entity is directly linked to Event entity (`origin.fk_event=event.id`)
    Boolean magnitudedirectlinktoorigin = false; // Boolean | Magnitude entity is directly linked to Origin entity (`magnitude.fk_origin=origin.id`)
    Boolean magnitudedirectlinktoevent = false; // Boolean | Magnitude entity is directly linked to Event entity `(magnitude.fk_origin=origin.id AND origin.fk_event=event.id`)
    String wheretypeoriginvaluein = "wheretypeoriginvaluein_example"; // String | Filter by type_origin.version_value (i.e. 0,1,200).
    String wheretypemagnitudenameregexp = "wheretypemagnitudenameregexp_example"; // String | Filter by type_magnitude.name using case-insensitive regexp (i.e. \"^ml.\\*\" or \"^ml.*|^mwp$\").
    List<String> whereeventlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"event.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereoriginlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> whereoriginlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"origin.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> wheremagnitudelocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"magnitude.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"whereoriginlocalspaceenvironmentin\".
    String whereeventlocalspacenamein = "whereeventlocalspacenamein_example"; // String | Filter by \"event.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereoriginlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String whereoriginlocalspacenamein = "whereoriginlocalspacenamein_example"; // String | Filter by \"origin.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String wheremagnitudelocalspacenamein = "wheremagnitudelocalspacenamein_example"; // String | Filter by \"magnitude.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"whereoriginlocalspacenamein\".
    OffsetDateTime eventupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"event.modified\" after; if \"originupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime originupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"origin.modified\" after; if \"eventupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime magnitudeupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"magnitude.modified\" after; if \"eventupdatedafter\" and/or \"originupdatedafter\" are set, the \"updatedafteroperator\" is used.
    String updatedafteroperator = "and"; // String | Set the \"operator\" to use when \"eventupdatedafter\", \"originupdatedafter\" and \"magnitudeupdatedafter\" are set.
    String whereflagsin = "whereflagsin_example"; // String | Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \"OR\".
    String orderby = "orderby_example"; // String | Select \"order by\"; multiple \"order\" contatenation available (i.e. event_id-desc,type_origin_version_value-asc)
    Long eventGroupId = 56L; // Long | Select events with same event_group_id.
    Long idLocalspace = 56L; // Long | Localspace Id.
    Integer limit = 56; // Integer | Limit the results to the specified number of records.
    Integer page = 56; // Integer | Pagination.
    Long eventid = 56L; // Long | Select by event id.
    Long originid = 56L; // Long | Select by origin id.
    Long magnitudeid = 56L; // Long | Select by magnitude id.
    try {
      GetEventsGroup200Response result = apiInstance.getMagnitudes(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getMagnitudes");
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
| **orpolygon** | **String**| Specify a list of polygons to select data.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;orpolygon&#x3D;12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3&#x60;. | [optional] |
| **notinpolygon** | **String**| Specify a list of polygons to NOT select data within.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;notinpolygon&#x3D;12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8&#x60; | [optional] |
| **wherepolygonnamein** | [**List&lt;String&gt;**](String.md)| Specify a list of pre-set polygons.   Each poligon is &#x60;,&#x60; separated value.  * Example: &#x60;wherepolygonnamein&#x3D;area_confine_italia,area_vulcanica_italia&#x60; | [optional] [enum: settore_1_pol, settore_2_pol, settore_cat_pol, aree_vulcaniche_italia_2020, ov_aree_vulcani_mari, area_vulcanica_italia, area_confine_italia] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **minnphtot** | **Integer**| Specify minimum number of phases (P&amp;S) with weight &gt; 0.0. | [optional] |
| **mindistance** | **Double**| Specify minimum distance from the closest station (kilometers). | [optional] |
| **wheretypeeventnamein** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **wheretypeeventnamenotin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **whereoriginqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.quality\&quot; by comma separated value (i.e. AA,AB,BC). | [optional] [enum: AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **wheremagnitudemagqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.mag_quality\&quot; by comma separated value (i.e. A,B,BC,DD). | [optional] [enum: A, B, C, D, AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **mintypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 0). | [optional] |
| **maxtypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 1000). | [optional] |
| **origindirectlinktoevent** | **Boolean**| Origin entity is directly linked to Event entity (&#x60;origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoorigin** | **Boolean**| Magnitude entity is directly linked to Origin entity (&#x60;magnitude.fk_origin&#x3D;origin.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoevent** | **Boolean**| Magnitude entity is directly linked to Event entity &#x60;(magnitude.fk_origin&#x3D;origin.id AND origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **wheretypeoriginvaluein** | **String**| Filter by type_origin.version_value (i.e. 0,1,200). | [optional] |
| **wheretypemagnitudenameregexp** | **String**| Filter by type_magnitude.name using case-insensitive regexp (i.e. \&quot;^ml.\\*\&quot; or \&quot;^ml.*|^mwp$\&quot;). | [optional] |
| **whereeventlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereoriginlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **wheremagnitudelocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;whereoriginlocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereeventlocalspacenamein** | **String**| Filter by \&quot;event.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **whereoriginlocalspacenamein** | **String**| Filter by \&quot;origin.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **wheremagnitudelocalspacenamein** | **String**| Filter by \&quot;magnitude.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;whereoriginlocalspacenamein\&quot;. | [optional] |
| **eventupdatedafter** | **OffsetDateTime**| Limit data to \&quot;event.modified\&quot; after; if \&quot;originupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **originupdatedafter** | **OffsetDateTime**| Limit data to \&quot;origin.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **magnitudeupdatedafter** | **OffsetDateTime**| Limit data to \&quot;magnitude.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;originupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **updatedafteroperator** | **String**| Set the \&quot;operator\&quot; to use when \&quot;eventupdatedafter\&quot;, \&quot;originupdatedafter\&quot; and \&quot;magnitudeupdatedafter\&quot; are set. | [optional] [default to or] [enum: and, or] |
| **whereflagsin** | **String**| Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \&quot;OR\&quot;. | [optional] |
| **orderby** | **String**| Select \&quot;order by\&quot;; multiple \&quot;order\&quot; contatenation available (i.e. event_id-desc,type_origin_version_value-asc) | [optional] |
| **eventGroupId** | **Long**| Select events with same event_group_id. | [optional] |
| **idLocalspace** | **Long**| Localspace Id. | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of records. | [optional] |
| **page** | **Integer**| Pagination. | [optional] |
| **eventid** | **Long**| Select by event id. | [optional] |
| **originid** | **Long**| Select by origin id. | [optional] |
| **magnitudeid** | **Long**| Select by magnitude id. | [optional] |

### Return type

[**GetEventsGroup200Response**](GetEventsGroup200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getMunicipiDistanceKmPopolazione"></a>
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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getMunicipio"></a>
# **getMunicipio**
> GetMunicipio200Response getMunicipio(name)

This API returns the Italian \&quot;municipio\&quot; information by name.

This API returns the Italian \&quot;municipio\&quot; information, by name.

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    String name = "name_example"; // String | Specify the Italian \"municipio\" name.
    try {
      GetMunicipio200Response result = apiInstance.getMunicipio(name);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getMunicipio");
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
| **name** | **String**| Specify the Italian \&quot;municipio\&quot; name. | |

### Return type

[**GetMunicipio200Response**](GetMunicipio200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getOriginFlag"></a>
# **getOriginFlag**
> GetOriginFlag200Response getOriginFlag(originid, name, value, note)

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    Long originid = 56L; // Long | Select by origin id.
    String name = "name_example"; // String | Flag name
    Long value = 56L; // Long | Flag value
    String note = "note_example"; // String | Flag note
    try {
      GetOriginFlag200Response result = apiInstance.getOriginFlag(originid, name, value, note);
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
| **name** | **String**| Flag name | [optional] |
| **value** | **Long**| Flag value | [optional] |
| **note** | **String**| Flag note | [optional] |

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getOrigins"></a>
# **getOrigins**
> GetEventsGroup200Response getOrigins(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid)

This API returns all the preferred origins.

This API returns all the preferred origins

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    String orpolygon = "orpolygon_example"; // String | Specify a list of polygons to select data.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `orpolygon=12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3`.
    String notinpolygon = "notinpolygon_example"; // String | Specify a list of polygons to NOT select data within.   Each poligon is `|` separated values, with counterclockwise values like `<lon>,<lat>` and last couple must be like the first one.  * Example: `notinpolygon=12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8`
    List<String> wherepolygonnamein = Arrays.asList(); // List<String> | Specify a list of pre-set polygons.   Each poligon is `,` separated value.  * Example: `wherepolygonnamein=area_confine_italia,area_vulcanica_italia`
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double minmag = 3.4D; // Double | Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5).
    Double maxmag = 3.4D; // Double | Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3).
    Double mindepth = 3.4D; // Double | Specify minimum depth (kilometers), values increase positively with depth (i.e. 0).
    Double maxdepth = 3.4D; // Double | Specify maximum depth (kilometers), values increase positively with depth (i.e. 50).
    Integer minnphtot = 56; // Integer | Specify minimum number of phases (P&S) with weight > 0.0.
    Double mindistance = 3.4D; // Double | Specify minimum distance from the closest station (kilometers).
    List<String> wheretypeeventnamein = Arrays.asList(); // List<String> | Filter by \"event.type_event\" by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> wheretypeeventnamenotin = Arrays.asList(); // List<String> | Filter by \"event.type_event\" - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion).
    List<String> whereoriginqualityin = Arrays.asList(); // List<String> | Filter by \"origin.quality\" by comma separated value (i.e. AA,AB,BC).
    List<String> wheremagnitudemagqualityin = Arrays.asList(); // List<String> | Filter by \"magnitude.mag_quality\" by comma separated value (i.e. A,B,BC,DD).
    Long mintypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 0).
    Long maxtypeoriginvalue = 56L; // Long | Filter the output to type_origin.version_value (i.e. 1000).
    Boolean origindirectlinktoevent = false; // Boolean | Origin entity is directly linked to Event entity (`origin.fk_event=event.id`)
    Boolean magnitudedirectlinktoorigin = false; // Boolean | Magnitude entity is directly linked to Origin entity (`magnitude.fk_origin=origin.id`)
    Boolean magnitudedirectlinktoevent = false; // Boolean | Magnitude entity is directly linked to Event entity `(magnitude.fk_origin=origin.id AND origin.fk_event=event.id`)
    String wheretypeoriginvaluein = "wheretypeoriginvaluein_example"; // String | Filter by type_origin.version_value (i.e. 0,1,200).
    String wheretypemagnitudenameregexp = "wheretypemagnitudenameregexp_example"; // String | Filter by type_magnitude.name using case-insensitive regexp (i.e. \"^ml.\\*\" or \"^ml.*|^mwp$\").
    List<String> whereeventlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"event.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereoriginlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> whereoriginlocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"origin.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"wheremagnitudelocalspaceenvironmentin\".
    List<String> wheremagnitudelocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"magnitude.localspace.environment\" by comma separated value (i.e. development,staging); this parameter is in \"OR\" with \"whereeventlocalspaceenvironmentin\" and \"whereoriginlocalspaceenvironmentin\".
    String whereeventlocalspacenamein = "whereeventlocalspacenamein_example"; // String | Filter by \"event.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereoriginlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String whereoriginlocalspacenamein = "whereoriginlocalspacenamein_example"; // String | Filter by \"origin.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"wheremagnitudelocalspacenamein\".
    String wheremagnitudelocalspacenamein = "wheremagnitudelocalspacenamein_example"; // String | Filter by \"magnitude.localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \"OR\" with \"whereeventlocalspacenamein\" and \"whereoriginlocalspacenamein\".
    OffsetDateTime eventupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"event.modified\" after; if \"originupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime originupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"origin.modified\" after; if \"eventupdatedafter\" and/or \"magnitudeupdatedafter\" are set, the \"updatedafteroperator\" is used.
    OffsetDateTime magnitudeupdatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"magnitude.modified\" after; if \"eventupdatedafter\" and/or \"originupdatedafter\" are set, the \"updatedafteroperator\" is used.
    String updatedafteroperator = "and"; // String | Set the \"operator\" to use when \"eventupdatedafter\", \"originupdatedafter\" and \"magnitudeupdatedafter\" are set.
    String whereflagsin = "whereflagsin_example"; // String | Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \"OR\".
    String orderby = "orderby_example"; // String | Select \"order by\"; multiple \"order\" contatenation available (i.e. event_id-desc,type_origin_version_value-asc)
    Long eventGroupId = 56L; // Long | Select events with same event_group_id.
    Long idLocalspace = 56L; // Long | Localspace Id.
    Integer limit = 56; // Integer | Limit the results to the specified number of records.
    Integer page = 56; // Integer | Pagination.
    Long eventid = 56L; // Long | Select by event id.
    Long originid = 56L; // Long | Select by origin id.
    Long magnitudeid = 56L; // Long | Select by magnitude id.
    try {
      GetEventsGroup200Response result = apiInstance.getOrigins(starttime, endtime, minlat, maxlat, minlon, maxlon, orpolygon, notinpolygon, wherepolygonnamein, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, minmag, maxmag, mindepth, maxdepth, minnphtot, mindistance, wheretypeeventnamein, wheretypeeventnamenotin, whereoriginqualityin, wheremagnitudemagqualityin, mintypeoriginvalue, maxtypeoriginvalue, origindirectlinktoevent, magnitudedirectlinktoorigin, magnitudedirectlinktoevent, wheretypeoriginvaluein, wheretypemagnitudenameregexp, whereeventlocalspaceenvironmentin, whereoriginlocalspaceenvironmentin, wheremagnitudelocalspaceenvironmentin, whereeventlocalspacenamein, whereoriginlocalspacenamein, wheremagnitudelocalspacenamein, eventupdatedafter, originupdatedafter, magnitudeupdatedafter, updatedafteroperator, whereflagsin, orderby, eventGroupId, idLocalspace, limit, page, eventid, originid, magnitudeid);
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
| **orpolygon** | **String**| Specify a list of polygons to select data.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;orpolygon&#x3D;12,42,13,42,13,43,12,43,12,42|12.3,42.3,13.3,42.3,13.3,43.3,12.3,43.3,12.3,42.3&#x60;. | [optional] |
| **notinpolygon** | **String**| Specify a list of polygons to NOT select data within.   Each poligon is &#x60;|&#x60; separated values, with counterclockwise values like &#x60;&lt;lon&gt;,&lt;lat&gt;&#x60; and last couple must be like the first one.  * Example: &#x60;notinpolygon&#x3D;12.5,42,12.5,43,13,48,12.5,42|12.2,41.8,13.2,41.8,13.2,42.8,12.2,42.8,12.2,41.8&#x60; | [optional] |
| **wherepolygonnamein** | [**List&lt;String&gt;**](String.md)| Specify a list of pre-set polygons.   Each poligon is &#x60;,&#x60; separated value.  * Example: &#x60;wherepolygonnamein&#x3D;area_confine_italia,area_vulcanica_italia&#x60; | [optional] [enum: settore_1_pol, settore_2_pol, settore_cat_pol, aree_vulcaniche_italia_2020, ov_aree_vulcani_mari, area_vulcanica_italia, area_confine_italia] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **minmag** | **Double**| Limit to events with a magnitude larger than or equal to the specified minimum (i.e. 1.5). | [optional] |
| **maxmag** | **Double**| Limit to events with a magnitude smaller than or equal to the specified maximum (i.e. 7.3). | [optional] |
| **mindepth** | **Double**| Specify minimum depth (kilometers), values increase positively with depth (i.e. 0). | [optional] |
| **maxdepth** | **Double**| Specify maximum depth (kilometers), values increase positively with depth (i.e. 50). | [optional] |
| **minnphtot** | **Integer**| Specify minimum number of phases (P&amp;S) with weight &gt; 0.0. | [optional] |
| **mindistance** | **Double**| Specify minimum distance from the closest station (kilometers). | [optional] |
| **wheretypeeventnamein** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **wheretypeeventnamenotin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.type_event\&quot; - not in - by comma separated value (i.e. earthquake,not reported,collapse,explosion). | [optional] [enum: earthquake, not reported, anthropogenic event, collapse, cavity collapse, mine collapse, building collapse, explosion, accidental explosion, chemical explosion, controlled explosion, experimental explosion, industrial explosion, mining explosion, quarry blast, road cut, blasting levee, nuclear explosion, induced or triggered event, rock burst, reservoir loading, fluid injection, fluid extraction, crash, plane crash, train crash, boat crash, other event, atmospheric event, sonic boom, sonic blast, acoustic noise, thunder, avalanche, snow avalanche, debris avalanche, hydroacoustic event, ice quake, slide, landslide, rockslide, meteorite, volcanic eruption, not existing, testing, duplicate earthquake] |
| **whereoriginqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.quality\&quot; by comma separated value (i.e. AA,AB,BC). | [optional] [enum: AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **wheremagnitudemagqualityin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.mag_quality\&quot; by comma separated value (i.e. A,B,BC,DD). | [optional] [enum: A, B, C, D, AA, AB, AC, AD, BA, BB, BC, BD, CA, CB, CC, CD, DA, DB, DC, DD] |
| **mintypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 0). | [optional] |
| **maxtypeoriginvalue** | **Long**| Filter the output to type_origin.version_value (i.e. 1000). | [optional] |
| **origindirectlinktoevent** | **Boolean**| Origin entity is directly linked to Event entity (&#x60;origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoorigin** | **Boolean**| Magnitude entity is directly linked to Origin entity (&#x60;magnitude.fk_origin&#x3D;origin.id&#x60;) | [optional] [default to false] |
| **magnitudedirectlinktoevent** | **Boolean**| Magnitude entity is directly linked to Event entity &#x60;(magnitude.fk_origin&#x3D;origin.id AND origin.fk_event&#x3D;event.id&#x60;) | [optional] [default to false] |
| **wheretypeoriginvaluein** | **String**| Filter by type_origin.version_value (i.e. 0,1,200). | [optional] |
| **wheretypemagnitudenameregexp** | **String**| Filter by type_magnitude.name using case-insensitive regexp (i.e. \&quot;^ml.\\*\&quot; or \&quot;^ml.*|^mwp$\&quot;). | [optional] |
| **whereeventlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;event.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereoriginlocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;origin.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;wheremagnitudelocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **wheremagnitudelocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;magnitude.localspace.environment\&quot; by comma separated value (i.e. development,staging); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspaceenvironmentin\&quot; and \&quot;whereoriginlocalspaceenvironmentin\&quot;. | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **whereeventlocalspacenamein** | **String**| Filter by \&quot;event.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereoriginlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **whereoriginlocalspacenamein** | **String**| Filter by \&quot;origin.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;wheremagnitudelocalspacenamein\&quot;. | [optional] |
| **wheremagnitudelocalspacenamein** | **String**| Filter by \&quot;magnitude.localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole); this parameter is in \&quot;OR\&quot; with \&quot;whereeventlocalspacenamein\&quot; and \&quot;whereoriginlocalspacenamein\&quot;. | [optional] |
| **eventupdatedafter** | **OffsetDateTime**| Limit data to \&quot;event.modified\&quot; after; if \&quot;originupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **originupdatedafter** | **OffsetDateTime**| Limit data to \&quot;origin.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;magnitudeupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **magnitudeupdatedafter** | **OffsetDateTime**| Limit data to \&quot;magnitude.modified\&quot; after; if \&quot;eventupdatedafter\&quot; and/or \&quot;originupdatedafter\&quot; are set, the \&quot;updatedafteroperator\&quot; is used. | [optional] |
| **updatedafteroperator** | **String**| Set the \&quot;operator\&quot; to use when \&quot;eventupdatedafter\&quot;, \&quot;originupdatedafter\&quot; and \&quot;magnitudeupdatedafter\&quot; are set. | [optional] [default to or] [enum: and, or] |
| **whereflagsin** | **String**| Filter flags by comma separated values (i.e. DPC,twitter,shakemap4); values are in \&quot;OR\&quot;. | [optional] |
| **orderby** | **String**| Select \&quot;order by\&quot;; multiple \&quot;order\&quot; contatenation available (i.e. event_id-desc,type_origin_version_value-asc) | [optional] |
| **eventGroupId** | **Long**| Select events with same event_group_id. | [optional] |
| **idLocalspace** | **Long**| Localspace Id. | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of records. | [optional] |
| **page** | **Integer**| Pagination. | [optional] |
| **eventid** | **Long**| Select by event id. | [optional] |
| **originid** | **Long**| Select by origin id. | [optional] |
| **magnitudeid** | **Long**| Select by magnitude id. | [optional] |

### Return type

[**GetEventsGroup200Response**](GetEventsGroup200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getPick"></a>
# **getPick**
> GetPick200Response getPick(starttime, endtime, wherenetin, wherestain, wherechain, wherelocin, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, wherelocalspaceenvironmentin, wherelocalspacenamein, limit, page)

This API returns picks from DataBase

This API returns picks

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    OffsetDateTime starttime = OffsetDateTime.now(); // OffsetDateTime | Select date start (i.e. 2016-06-22T16:52:06.260Z).
    OffsetDateTime endtime = OffsetDateTime.now(); // OffsetDateTime | Select date end (i.e. 2016-06-22T16:52:06.260Z).
    String wherenetin = "wherenetin_example"; // String | Filter by multiple \"net\", comma separated value (i.e. IV,MN).
    String wherestain = "wherestain_example"; // String | Filter by multiple \"sta\", comma separated value (i.e. ACER,BADI).
    String wherechain = "wherechain_example"; // String | Filter by multiple \"cha\", comma separated value (i.e. HHZ,HHE).
    String wherelocin = "wherelocin_example"; // String | Filter by multiple \"loc\", comma separated value (i.e. 00,01,--).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers.
    List<String> wherelocalspaceenvironmentin = Arrays.asList(); // List<String> | Filter by \"localspace.environment\" by comma separated value (i.e. development,staging).
    String wherelocalspacenamein = "wherelocalspacenamein_example"; // String | Filter by \"localspace.name\" by comma separated value (i.e. hew10_mole,hew20_mole).
    Integer limit = 56; // Integer | Limit the results to the specified number of records.
    Integer page = 56; // Integer | Pagination.
    try {
      GetPick200Response result = apiInstance.getPick(starttime, endtime, wherenetin, wherestain, wherechain, wherelocin, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, wherelocalspaceenvironmentin, wherelocalspacenamein, limit, page);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getPick");
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
| **wherenetin** | **String**| Filter by multiple \&quot;net\&quot;, comma separated value (i.e. IV,MN). | [optional] |
| **wherestain** | **String**| Filter by multiple \&quot;sta\&quot;, comma separated value (i.e. ACER,BADI). | [optional] |
| **wherechain** | **String**| Filter by multiple \&quot;cha\&quot;, comma separated value (i.e. HHZ,HHE). | [optional] |
| **wherelocin** | **String**| Filter by multiple \&quot;loc\&quot;, comma separated value (i.e. 00,01,--). | [optional] |
| **minlat** | **Double**| Specify southern boundary for search in WGS84 (i.e. 39.12). | [optional] |
| **maxlat** | **Double**| Specify northern boundary for search in WGS84 (i.e. 46.52). | [optional] |
| **minlon** | **Double**| Specify western boundary for search in WGS84 (i.e. 10.12). | [optional] |
| **maxlon** | **Double**| Specify eastern boundary for search (in WGS84) (i.e. 15.12). | [optional] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **wherelocalspaceenvironmentin** | [**List&lt;String&gt;**](String.md)| Filter by \&quot;localspace.environment\&quot; by comma separated value (i.e. development,staging). | [optional] [enum: development, testing, staging, production, external, catalog, generic] |
| **wherelocalspacenamein** | **String**| Filter by \&quot;localspace.name\&quot; by comma separated value (i.e. hew10_mole,hew20_mole). | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of records. | [optional] |
| **page** | **Integer**| Pagination. | [optional] |

### Return type

[**GetPick200Response**](GetPick200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getProvenance"></a>
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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getRegionName"></a>
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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getScnl"></a>
# **getScnl**
> GetScnl200Response getScnl(wherenetin, wherestain, wherechain, wherelocin, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, wherelatorlonarenull, updatedafter, limit, page)

This API returns scnls from DataBase

This API returns scnls

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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

    GetApi apiInstance = new GetApi(defaultClient);
    String wherenetin = "wherenetin_example"; // String | Filter by multiple \"net\", comma separated value (i.e. IV,MN).
    String wherestain = "wherestain_example"; // String | Filter by multiple \"sta\", comma separated value (i.e. ACER,BADI).
    String wherechain = "wherechain_example"; // String | Filter by multiple \"cha\", comma separated value (i.e. HHZ,HHE).
    String wherelocin = "wherelocin_example"; // String | Filter by multiple \"loc\", comma separated value (i.e. 00,01,--).
    Double minlat = 3.4D; // Double | Specify southern boundary for search in WGS84 (i.e. 39.12).
    Double maxlat = 3.4D; // Double | Specify northern boundary for search in WGS84 (i.e. 46.52).
    Double minlon = 3.4D; // Double | Specify western boundary for search in WGS84 (i.e. 10.12).
    Double maxlon = 3.4D; // Double | Specify eastern boundary for search (in WGS84) (i.e. 15.12).
    Double lat = 3.4D; // Double | Specify the central latitude point for a radial search in WGS84 (i.e. 42).
    Double lon = 3.4D; // Double | Specify the central longitude point for a radial search in WGS84 (i.e. 12).
    Double minradius = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5).
    Double maxradius = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5).
    Double minradiuskm = 3.4D; // Double | Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers.
    Double maxradiuskm = 3.4D; // Double | Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers.
    Boolean wherelatorlonarenull = true; // Boolean | fileter by 'lat' or 'lon' set to 'null'
    OffsetDateTime updatedafter = OffsetDateTime.now(); // OffsetDateTime | Limit data to \"updated after\" params.
    Integer limit = 56; // Integer | Limit the results to the specified number of records.
    Integer page = 56; // Integer | Pagination.
    try {
      GetScnl200Response result = apiInstance.getScnl(wherenetin, wherestain, wherechain, wherelocin, minlat, maxlat, minlon, maxlon, lat, lon, minradius, maxradius, minradiuskm, maxradiuskm, wherelatorlonarenull, updatedafter, limit, page);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling GetApi#getScnl");
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
| **wherenetin** | **String**| Filter by multiple \&quot;net\&quot;, comma separated value (i.e. IV,MN). | [optional] |
| **wherestain** | **String**| Filter by multiple \&quot;sta\&quot;, comma separated value (i.e. ACER,BADI). | [optional] |
| **wherechain** | **String**| Filter by multiple \&quot;cha\&quot;, comma separated value (i.e. HHZ,HHE). | [optional] |
| **wherelocin** | **String**| Filter by multiple \&quot;loc\&quot;, comma separated value (i.e. 00,01,--). | [optional] |
| **minlat** | **Double**| Specify southern boundary for search in WGS84 (i.e. 39.12). | [optional] |
| **maxlat** | **Double**| Specify northern boundary for search in WGS84 (i.e. 46.52). | [optional] |
| **minlon** | **Double**| Specify western boundary for search in WGS84 (i.e. 10.12). | [optional] |
| **maxlon** | **Double**| Specify eastern boundary for search (in WGS84) (i.e. 15.12). | [optional] |
| **lat** | **Double**| Specify the central latitude point for a radial search in WGS84 (i.e. 42). | [optional] |
| **lon** | **Double**| Specify the central longitude point for a radial search in WGS84 (i.e. 12). | [optional] |
| **minradius** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 1.5). | [optional] |
| **maxradius** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude in Degrees (i.e. 5). | [optional] |
| **minradiuskm** | **Double**| Specify minimum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **maxradiuskm** | **Double**| Specify maximum distance from the geographic point defined by latitude and longitude. Kilometers. | [optional] |
| **wherelatorlonarenull** | **Boolean**| fileter by &#39;lat&#39; or &#39;lon&#39; set to &#39;null&#39; | [optional] |
| **updatedafter** | **OffsetDateTime**| Limit data to \&quot;updated after\&quot; params. | [optional] |
| **limit** | **Integer**| Limit the results to the specified number of records. | [optional] |
| **page** | **Integer**| Pagination. | [optional] |

### Return type

[**GetScnl200Response**](GetScnl200Response.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/problem+json, application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getTypeEvent"></a>
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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getTypeMagnitude"></a>
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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

<a id="getTypeOrigin"></a>
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
    defaultClient.setBasePath("https://caravel-dante.int.ingv.it/api");

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
| **204** | Request was properly formatted and submitted but no data matches the selection |  -  |
| **404** | Not Found |  -  |
| **400** | Bad Request |  -  |
| **422** | Unprocessable Entity |  -  |
| **429** | Too many requests |  * Retry-After -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **503** | Service Unavailable |  * Retry-After -  <br>  |
| **500** | Internal Server Error |  -  |
| **200** | Operation successful |  * Cache-Control -  <br>  * X-RateLimit-Limit -  <br>  * X-RateLimit-Remaining -  <br>  * X-RateLimit-Reset -  <br>  |
| **0** | Unexpected error |  -  |

