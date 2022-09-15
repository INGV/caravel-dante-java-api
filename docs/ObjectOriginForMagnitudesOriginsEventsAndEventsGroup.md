

# ObjectOriginForMagnitudesOriginsEventsAndEventsGroup


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**localspace** | **String** | Localspace name. i.e. hew1_mole, endeavour_mole | char(255) |  [optional] |
|**ot** | **OffsetDateTime** | Origin time | datetime(3) |  [optional] |
|**lat** | **Double** | Latitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  [optional] |
|**lon** | **Double** | Longitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  [optional] |
|**depth** | **Double** | Depth in Km | double |  [optional] |
|**errOt** | **Double** | Origin time error | double |  [optional] |
|**errH** | **Double** | Depth error | double |  [optional] |
|**errZ** | **Double** | Depth error | double |  [optional] |
|**errLat** | **Double** | Latitude error | double |  [optional] |
|**errLon** | **Double** | Longitude error | double |  [optional] |
|**quality** | **String** | Quality of the localization | char(2) |  [optional] |
|**associatedPhaseCount** | **Long** | Number of associated phases, regardless of their use for origin computation | int(8)&#39; |  [optional] |
|**associatedStationCount** | **Long** | Number of stations at which the event was observed | int(8)&#39; |  [optional] |
|**usedPhaseCount** | **Long** | Number of defining phases, i.e., phase observations that were actually used for computing the origin | int(8)&#39; |  [optional] |
|**usedStationCount** | **Long** | Number of stations from which data was used for origin computation | int(8)&#39; |  [optional] |
|**region** | **String** | Event location remark region | varchar(255) |  [optional] |
|**flags** | **String** | Flags for origin | varchar(255) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**typeOrigin** | [**ObjectTypeOrigin**](ObjectTypeOrigin.md) |  |  [optional] |
|**provenance** | [**ObjectProvenaceForMagnitudesOriginsEventsAndEventsGroup**](ObjectProvenaceForMagnitudesOriginsEventsAndEventsGroup.md) |  |  [optional] |



