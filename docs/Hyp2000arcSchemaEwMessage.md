

# Hyp2000arcSchemaEwMessage


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**quakeId** | **Long** | Localspace Id | bigint(19) |  |
|**version** | **TypeOriginName** |  |  |
|**originTime** | **OffsetDateTime** | Origin time | datetime(3) |  |
|**latitude** | **Double** | Latitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  |
|**longitude** | **Double** | Longitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  |
|**depth** | **Double** | Depth in Km | double |  |
|**nph** | **Long** | # arrivals (P&amp;S) weight &gt;0.1 | int(11) |  [optional] |
|**nphS** | **Long** | # S arrivals weight &gt;0.1 | int(11) |  [optional] |
|**nphtot** | **Long** | # arrivals (P&amp;S) weight &gt;0.0 | int(11) |  [optional] |
|**nPfm** | **Long** | # P first motions | int(11) |  [optional] |
|**gap** | **Float** | Azimutal gap | float4 |  [optional] |
|**dmin** | **Double** | dmin description | ??? |  [optional] |
|**rms** | **Double** | Root mean square | double |  [optional] |
|**e0az** | **Float** | azimuth of largest principal error | double |  [optional] |
|**e0dp** | **Double** | dip of largest principal error | double |  [optional] |
|**e0** | **Double** | largest principal error | double |  [optional] |
|**e1az** | **Float** | azimuth of intermediate principal error | double |  [optional] |
|**e1dp** | **Double** | dip of intermediate principal error | double |  [optional] |
|**e1** | **Double** | intermed principal error | double |  [optional] |
|**e2** | **Double** | smallest principal error | double |  [optional] |
|**erh** | **Double** | Depth error | double |  [optional] |
|**erz** | **Double** | Depth error | double |  [optional] |
|**md** | **Double** | Md description | ??? |  [optional] |
|**reg** | **String** | ingvQuality description | ??? |  [optional] |
|**labelpref** | **String** | ingvQuality description | ??? |  [optional] |
|**mpref** | **Double** | Mpref description | ??? |  [optional] |
|**wtpref** | **Double** | wtpref description | ??? |  [optional] |
|**mdtype** | **String** | ingvQuality description | ??? |  [optional] |
|**mdmad** | **Double** | mdmad description | ??? |  [optional] |
|**mdwt** | **Double** | mdwt description | ??? |  [optional] |
|**ingvQuality** | **String** | ingvQuality description | ??? |  [optional] |
|**phases** | [**List&lt;Hyp2000arcPhasesInner&gt;**](Hyp2000arcPhasesInner.md) |  |  [optional] |



