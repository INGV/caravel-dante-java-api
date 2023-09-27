

# ObjectArrival


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**iscCode** | **String** | ISC arrival code | varchar(8) |  |
|**epDistanceKm** | **Float** | Distance from epicenter of the station expressed in Km | double |  [optional] |
|**epDistanceDelta** | **Float** | Distance from epicenter of the station expressed in Degrees | double |  [optional] |
|**origDistanceKm** | **Double** | Distance from origin of the station (km) | double |  [optional] |
|**azimut** | **Float** | Station origin azimut | double |  [optional] |
|**takeOff** | **Float** | Take off angle | double |  [optional] |
|**polarityIsUsed** | **Boolean** | 1 if it is used for polarity calculation | boolean |  [optional] |
|**arrTimeIsUsed** | **Boolean** | 1 if it is used for origin calculation | boolean |  [optional] |
|**residual** | **Double** | Residual | double |  [optional] |
|**weight** | **Double** | Weight | double |  [optional] |
|**pick** | [**ObjectPick**](ObjectPick.md) |  |  [optional] |



