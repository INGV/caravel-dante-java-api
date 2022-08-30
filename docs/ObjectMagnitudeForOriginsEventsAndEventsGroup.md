

# ObjectMagnitudeForOriginsEventsAndEventsGroup


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**localspace** | **String** | Localspace name. i.e. hew1_mole, endeavour_mole | char(255) |  [optional] |
|**mag** | **Double** | Magnitude value | double |  [optional] |
|**typeMagnitude** | **String** | Type of the magnitude | varchar(255) |  [optional] |
|**lowerUncertainty** | **Double** | Magnitude lower_uncertainty | double |  [optional] |
|**upperUncertainty** | **Double** | Magnitude upper_uncertainty | double |  [optional] |
|**quality** | **Double** | quality | double |  [optional] |
|**magQuality** | **String** | INGV quality code of the magnitude (computed by ew2moledb) | char(2) |  [optional] |
|**originid** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**provenance** | [**ObjectProvenaceForOriginsEventsAndEventsGroup**](ObjectProvenaceForOriginsEventsAndEventsGroup.md) |  |  [optional] |



