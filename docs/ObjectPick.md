

# ObjectPick


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**net** | **String** | Channel net code | char(2) |  |
|**sta** | **String** | Channel station code | varchar(5) |  |
|**cha** | **String** | Channel code | char(3) |  |
|**loc** | **String** | Channel location | char(2) |  [optional] |
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**qualityClass** | **Integer** | Pick quality class | bigint |  [optional] |
|**lowerUncertainty** | **Float** | Uncertainty as the absolute value of deviation from the mainvalue towards smaller values. | decimal(8,3) |  [optional] |
|**upperUncertainty** | **Float** | Uncertainty as the absolute value of deviation from the mainvalue towards larger values. | decimal(8,3) |  [optional] |
|**confidenceLevel** | **Float** | Integer numer for confidence level type (68.3 1 sigma, xx &#x3D;2 sigma, 99% 3 sigma) | decimal(5.2) |  [optional] |
|**arrivalTime** | **OffsetDateTime** | Arrival time with microseconds | datetime(3) |  |
|**firstmotion** | **PickFirstmotion** |  |  [optional] |
|**emersio** | **PickEmersio** |  |  [optional] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |



