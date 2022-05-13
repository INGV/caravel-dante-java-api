

# StrongmotioniiBaseEwMessage


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**quakeId** | **Long** | Localspace Id | bigint(19) |  |
|**version** | **TypeOriginName** |  |  |
|**network** | **String** | Channel net code | char(2) |  [optional] |
|**station** | **String** | Channel station code | varchar(5) |  [optional] |
|**component** | **String** | Channel code | char(3) |  [optional] |
|**location** | **String** | Channel location | char(2) |  [optional] |
|**qAuthor** | **String** | qAuthor description |  [optional] |
|**time** | **OffsetDateTime** | time: trigger reported by SM box - datetime part | datetime(6) |  [optional] |
|**alternateTime** | **OffsetDateTime** | alternate time: trigger reported by SM box - time with microseconds | datetime(3) |  [optional] |
|**alternateCode** | **Long** | code specifying the source of the alternate time field | int(11) |  [optional] |
|**pga** | **Float** | REQUIRED: peak ground acceleration (cm/s/s) | double |  [optional] |
|**pgaTime** | **OffsetDateTime** | OPTIONAL: time of pga - datetime part | datetime(3) |  [optional] |
|**pgv** | **Float** | REQUIRED: peak ground velocity (cm/s) | double |  [optional] |
|**pgvTime** | **OffsetDateTime** | OPTIONAL: time of pgv - datetime part | datetime(3) |  [optional] |
|**pgd** | **Float** | REQUIRED: peak ground displacement (cm) | double |  [optional] |
|**pgdTime** | **OffsetDateTime** | OPTIONAL: time of pgd - datetime part | datetime(3) |  [optional] |
|**RSA** | [**List&lt;StrongmotioniiBaseEwMessageRSAInner&gt;**](StrongmotioniiBaseEwMessageRSAInner.md) |  |  [optional] |



