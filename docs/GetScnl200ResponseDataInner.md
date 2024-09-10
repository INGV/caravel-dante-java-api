

# GetScnl200ResponseDataInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**net** | **String** | Channel net code | char(2) |  [optional] |
|**sta** | **String** | Channel station code | varchar(5) |  [optional] |
|**cha** | **String** | Channel code | char(3) |  [optional] |
|**loc** | **String** | Channel location | char(2) |  [optional] |
|**lat** | **Double** | Latitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  [optional] |
|**lon** | **Double** | Longitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  [optional] |
|**elev** | **Double** | Elevation in meter | double |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |



