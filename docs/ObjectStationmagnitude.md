

# ObjectStationmagnitude


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**net** | **String** | Channel net code | char(2) |  [optional] |
|**sta** | **String** | Channel station code | varchar(5) |  [optional] |
|**cha** | **String** | Channel code | char(3) |  [optional] |
|**loc** | **String** | Channel location | char(2) |  [optional] |
|**category** | **TypeAmplitudeCategory** |  |  [optional] |
|**timewindowReference** | **OffsetDateTime** | Describes a time window for amplitude measurements, given by a central point in time |  [optional] [readonly] |
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**pickId** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**time1** | **OffsetDateTime** |  | datetime(3) |  [optional] |
|**amp1** | **Double** | Amplitude value | double |  |
|**period** | **Double** | Amlitude period | double |  [optional] |
|**time2** | **OffsetDateTime** |  | datetime(3) |  [optional] |
|**amp2** | **Double** | Amplitude value | double |  |
|**revised** | **Integer** | Dichiara se tale ampiezza è stata rivista dall&#39;analista, eventualmente anche non modificata, oppure no. (1/0, true/false) | tinyint(3) |  [optional] |
|**typeAmplitude** | [**ObjectStationmagnitudeTypeAmplitude**](ObjectStationmagnitudeTypeAmplitude.md) |  |  [optional] |
|**epDistance** | **Float** | Distance from epicenter of the station expressed in Km | double |  [optional] |
|**origDistance** | **Double** | Distance from origin of the station | double |  [optional] |
|**azimut** | **Float** | Station origin azimut | double |  [optional] |
|**mag** | **Double** | Amplitude magnitude value | double |  [optional] |
|**errMag** | **Double** | magnitude error | double |  [optional] |
|**weight** | **Double** | Weight | double |  [optional] |
|**magCorrection** | **Double** | magnitude correction | double |  [optional] |
|**isUsed** | **Boolean** | true if used | boolean |  [optional] |
|**typeMagnitude** | **String** | Type of the magnitude | varchar(255) |  [optional] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |



