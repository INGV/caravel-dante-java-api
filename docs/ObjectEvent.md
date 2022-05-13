

# ObjectEvent


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**typeEvent** | **String** | Name | varchar(255) |  |
|**eventGroupId** | **Long** | Link event group | bigint(20) |  [optional] [readonly] |
|**preferredOriginId** | **Long** | Link: preferred origin. It can be NULL. | bigint(20) |  [optional] [readonly] |
|**preferredMagnitudeId** | **Long** | Link: preferred magnitude. It can be NULL. | bigint(20) |  [optional] [readonly] |
|**preferredFocalmechanismId** | **Long** | Link: preferred focalmechanism. It can be NULL. | bigint(20) |  [optional] [readonly] |
|**typeGroup** | **Long** | Group type. Used by clustering algorithm | tinyint(4) |  [optional] [readonly] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**origins** | [**List&lt;ObjectOrigin&gt;**](ObjectOrigin.md) |  |  [optional] |
|**strongmotions** | [**List&lt;ObjectStrongmotion&gt;**](ObjectStrongmotion.md) |  |  [optional] |



