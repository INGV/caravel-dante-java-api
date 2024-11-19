

# ObjectStationmagnitude


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**epDistanceKm** | **Float** | Distance from epicenter of the station expressed in Km | double |  [optional] |
|**origDistanceKm** | **Double** | Distance from origin of the station (km) | double |  [optional] |
|**azimut** | **Float** | Station origin azimut | double |  [optional] |
|**mag** | **Double** | Amplitude magnitude value | double |  |
|**errMag** | **Double** | magnitude error | double |  [optional] |
|**weight** | **Double** | Weight | double |  [optional] |
|**magCorrection** | **Double** | magnitude correction | double |  [optional] |
|**isUsed** | **Boolean** | true if used | boolean |  [optional] |
|**typeMagnitude** | **String** | Type Scale of the magnitude, international scale label (i.e. ML, Md, Mw, ...) | varchar(50) |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**amplitude** | [**ObjectAmplitude**](ObjectAmplitude.md) |  |  [optional] |



