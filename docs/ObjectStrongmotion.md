

# ObjectStrongmotion


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**net** | **String** | Channel net code | char(2) |  [optional] |
|**sta** | **String** | Channel station code | varchar(5) |  [optional] |
|**cha** | **String** | Channel code | char(3) |  [optional] |
|**loc** | **String** | Channel location | char(2) |  [optional] |
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**tDt** | **OffsetDateTime** | time: trigger reported by SM box - datetime part | datetime(6) |  |
|**pga** | **Float** | REQUIRED: peak ground acceleration (cm/s/s) | double |  [optional] |
|**tpgaDt** | **OffsetDateTime** | OPTIONAL: time of pga - datetime part | datetime(3) |  [optional] |
|**pgv** | **Float** | REQUIRED: peak ground velocity (cm/s) | double |  [optional] |
|**tpgvDt** | **OffsetDateTime** | OPTIONAL: time of pgv - datetime part | datetime(3) |  [optional] |
|**pgd** | **Float** | REQUIRED: peak ground displacement (cm) | double |  [optional] |
|**tpgdDt** | **OffsetDateTime** | OPTIONAL: time of pgd - datetime part | datetime(3) |  [optional] |
|**rsa030** | **Float** | RSA(response spectrum accel) value for period 0.30 | double |  [optional] |
|**rsa100** | **Float** | RSA(response spectrum accel) value for period 1.00 | double |  [optional] |
|**rsa300** | **Float** | RSA(response spectrum accel) value for period 3.00 | double |  [optional] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |
|**alternative** | [**ObjectStrongmotionAlternative**](ObjectStrongmotionAlternative.md) |  |  [optional] |
|**rsa** | [**List&lt;ObjectStrongmotionRsaInner&gt;**](ObjectStrongmotionRsaInner.md) |  |  [optional] |



