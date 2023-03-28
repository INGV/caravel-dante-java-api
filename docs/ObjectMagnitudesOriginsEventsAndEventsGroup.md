

# ObjectMagnitudesOriginsEventsAndEventsGroup


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**localspace** | **String** | Localspace name. i.e. hew1_mole, endeavour_mole | char(255) |  [optional] |
|**eventGroupId** | **Long** | Link event group | bigint(20) |  [optional] [readonly] |
|**preferredOriginId** | **Long** | Link: preferred origin. It can be NULL. | bigint(20) |  [optional] [readonly] |
|**preferredMagnitudeId** | **Long** | Link: preferred magnitude. It can be NULL. | bigint(20) |  [optional] [readonly] |
|**preferredFocalmechanismId** | **Long** | Link: preferred focalmechanism. It can be NULL. | bigint(20) |  [optional] [readonly] |
|**flags** | **String** | Flags for origin | varchar(255) |  [optional] [readonly] |
|**typeGroup** | **Long** | Group type. Used by clustering algorithm | tinyint(4) |  [optional] [readonly] |
|**typeEvent** | **String** | Name | varchar(255) |  [optional] |
|**origindirectlinktoevent** | **Boolean** | Origin entity is directly linked to Event entity (origin.fk_event&#x3D;event.id) |  [optional] |
|**magnitudedirectlinktoorigin** | **Boolean** | Magnitude entity is directly linked to Origin entity (magnitude.fk_origin&#x3D;origin.id) |  [optional] |
|**magnitudedirectlinktoevent** | **Boolean** | Magnitude entity is directly linked to Event entity (magnitude.fk_origin&#x3D;origin.id -&gt; origin.fk_event&#x3D;event.id) |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**origin** | [**ObjectOriginForMagnitudesOriginsEventsAndEventsGroup**](ObjectOriginForMagnitudesOriginsEventsAndEventsGroup.md) |  |  [optional] |
|**magnitude** | [**ObjectMagnitudeForMagnitudesOriginsEventsAndEventsGroup**](ObjectMagnitudeForMagnitudesOriginsEventsAndEventsGroup.md) |  |  [optional] |
|**provenance** | [**ObjectProvenaceForMagnitudesOriginsEventsAndEventsGroup**](ObjectProvenaceForMagnitudesOriginsEventsAndEventsGroup.md) |  |  [optional] |



