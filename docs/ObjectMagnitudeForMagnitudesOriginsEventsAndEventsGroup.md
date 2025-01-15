

# ObjectMagnitudeForMagnitudesOriginsEventsAndEventsGroup


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**mag** | **Double** | Magnitude value | double |  [optional] |
|**typeMagnitude** | **String** | Type Scale of the magnitude, international scale label (i.e. ML, Md, Mw, ...) | varchar(50) |  [optional] |
|**typeMagnitudeExtended** | **String** | Type of the magnitude | varchar(255) |  [optional] |
|**lowerUncertainty** | **Double** | Magnitude lower_uncertainty | double |  [optional] |
|**upperUncertainty** | **Double** | Magnitude upper_uncertainty | double |  [optional] |
|**quality** | **Double** | quality | double |  [optional] |
|**magQuality** | **String** | INGV quality code of the magnitude (computed by ew2moledb) | char(2) |  [optional] |
|**originid** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**localspace** | [**ObjectLocalspaceForVw**](ObjectLocalspaceForVw.md) |  |  [optional] |
|**provenance** | [**ObjectProvenaceForMagnitudesOriginsEventsAndEventsGroup**](ObjectProvenaceForMagnitudesOriginsEventsAndEventsGroup.md) |  |  [optional] |



