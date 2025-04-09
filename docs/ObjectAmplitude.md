

# ObjectAmplitude


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**net** | **String** | Channel net code | char(2) |  [optional] |
|**sta** | **String** | Channel station code | varchar(5) |  [optional] |
|**cha** | **String** | Channel code | char(3) |  [optional] |
|**loc** | **String** | Channel location | char(2) |  [optional] |
|**time1** | **OffsetDateTime** |  | datetime(3) |  |
|**amp1** | **Double** | Amplitude value | double |  |
|**time2** | **OffsetDateTime** |  | datetime(3) |  [optional] |
|**amp2** | **Double** | Amplitude value | double |  [optional] |
|**pickId** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**period** | **Double** | Amlitude period | double |  [optional] |
|**revised** | **Integer** | Dichiara se tale ampiezza è stata rivista dall&#39;analista, eventualmente anche non modificata, oppure no. (1/0, true/false) | tinyint(3) |  [optional] |
|**typeAmplitude** | [**ObjectAmplitudeTypeAmplitude**](ObjectAmplitudeTypeAmplitude.md) |  |  [optional] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**timewindowReference** | **OffsetDateTime** | Describes a time window for amplitude measurements, given by a central point in time |  [optional] [readonly] |



