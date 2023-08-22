

# ObjectStationmagnitude


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**epDistance** | **Float** | Distance from epicenter of the station expressed in Km | double |  [optional] |
|**origDistance** | **Double** | Distance from origin of the station | double |  [optional] |
|**azimut** | **Float** | Station origin azimut | double |  [optional] |
|**mag** | **Double** | Amplitude magnitude value | double |  |
|**errMag** | **Double** | magnitude error | double |  [optional] |
|**weight** | **Double** | Weight | double |  [optional] |
|**magCorrection** | **Double** | magnitude correction | double |  [optional] |
|**isUsed** | **Boolean** | true if used | boolean |  [optional] |
|**typeMagnitude** | **String** | Type of the magnitude | varchar(255) |  [optional] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**amplitude** | [**ObjectAmplitude**](ObjectAmplitude.md) |  |  [optional] |



