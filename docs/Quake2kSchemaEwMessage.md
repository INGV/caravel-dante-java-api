

# Quake2kSchemaEwMessage


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**quakeId** | **Long** | Localspace Id | bigint(19) |  |
|**originTime** | **OffsetDateTime** | Origin time | datetime(3) |  |
|**latitude** | **Double** | Latitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  |
|**longitude** | **Double** | Longitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  |
|**depth** | **Double** | Depth in Km | double |  |
|**rms** | **Double** | Root mean square | double |  [optional] |
|**dmin** | **Double** | dmin description | ??? |  [optional] |
|**ravg** | **Double** | ravg description | ??? |  [optional] |
|**gap** | **Float** | Azimutal gap | float4 |  [optional] |
|**nph** | **Long** | # arrivals (P&amp;S) weight &gt;0.1 | int(11) |  [optional] |



