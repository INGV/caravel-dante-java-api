

# ObjectMagnitude


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**mag** | **Double** | Magnitude value | double |  |
|**lowerUncertainty** | **Double** | Magnitude lower_uncertainty | double |  [optional] |
|**upperUncertainty** | **Double** | Magnitude upper_uncertainty | double |  [optional] |
|**confidenceLevel** | **Float** | Integer numer for confidence level type (68.3 1 sigma, xx &#x3D;2 sigma, 99% 3 sigma) | decimal(5.2) |  [optional] |
|**quality** | **Double** | quality | double |  [optional] |
|**minDistance** | **Double** | Minimal distance from station to origin | double |  [optional] |
|**azimut** | **Float** | Azimutal gap | float4 |  [optional] |
|**nsta** | **Long** | Number of the stations on magnitudo calculation | int(11) |  [optional] |
|**ncha** | **Long** | Number of the channel on magnitudo calculation | int(11) |  [optional] |
|**nstaUsed** | **Long** | Number of the stations used on magnitudo calculation | int(11) |  [optional] |
|**nchaUsed** | **Long** | Number of the channels used on magnitude calculation | int(11) |  [optional] |
|**magQuality** | **String** | INGV quality code of the magnitude (computed by ew2moledb) | char(2) |  [optional] |
|**typeMagnitude** | **String** | Type Scale of the magnitude, international scale label (i.e. ML, Md, Mw, ...) | varchar(50) |  |
|**typeMagnitudeExtended** | **String** | Type of the magnitude | varchar(255) |  [optional] |
|**typeMagnitudePriority** | **Long** | Priority | int(8) |  [optional] [readonly] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |
|**stationmagnitudes** | [**List&lt;ObjectStationmagnitude&gt;**](ObjectStationmagnitude.md) |  |  [optional] |



