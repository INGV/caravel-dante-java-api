

# ObjectOrigin


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**azimGap** | **Float** | Azimutal gap | float4 |  [optional] |
|**confidenceLevel** | **Float** | Integer numer for confidence level type (68.3 1 sigma, xx &#x3D;2 sigma, 99% 3 sigma) | decimal(5.2) |  [optional] |
|**depth** | **Double** | Depth in Km | double |  |
|**e0** | **Double** | largest principal error | double |  [optional] |
|**e0Az** | **Float** | azimuth of largest principal error | double |  [optional] |
|**e0Dip** | **Double** | dip of largest principal error | double |  [optional] |
|**e1** | **Double** | intermed principal error | double |  [optional] |
|**e1Az** | **Float** | azimuth of intermediate principal error | double |  [optional] |
|**e1Dip** | **Double** | dip of intermediate principal error | double |  [optional] |
|**e2** | **Double** | smallest principal error | double |  [optional] |
|**e2Az** | **Float** | azimuth of smallest principal error | double |  [optional] |
|**e2Dip** | **Long** | dip of smallest principal error | double |  [optional] |
|**errDepth** | **Double** | Depth error | double |  [optional] |
|**errH** | **Double** | Horizontal error (km) | double |  [optional] |
|**errLat** | **Double** | Latitude error (km) | double |  [optional] |
|**errLon** | **Double** | Longitude error (km) | double |  [optional] |
|**errOt** | **Double** | Origin time error | double |  [optional] |
|**errZ** | **Double** | Depth error (km) | double |  [optional] |
|**fixDepth** | **Boolean** | true if depth is fixed | boolean |  [optional] |
|**isCentroid** | **Boolean** | true if it is a centroi | boolean |  [optional] |
|**lat** | **Double** | Latitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  |
|**lon** | **Double** | Longitude of a point expressed in:  * the ETRS89 system for Italian and European territories * and in WGS84 for the others. |  |
|**maxDistance** | **Double** | Distance from the furthest station (km) | double |  [optional] |
|**medDistance** | **Double** | Median distance from the epicenter to the used stations (km) | double |  [optional] |
|**minDistance** | **Double** | Distance from the closest station (km) | double |  [optional] |
|**nph** | **Long** | # arrivals (P&amp;S) weight &gt;0.1 | int(11) |  [optional] |
|**nphFm** | **Long** | # P first motions | int(11) |  [optional] |
|**nphS** | **Long** | # S arrivals weight &gt;0.1 | int(11) |  [optional] |
|**nphTot** | **Long** | # arrivals (P&amp;S) weight &gt;0.0 | int(11) |  [optional] |
|**ot** | **OffsetDateTime** | Origin time | datetime(3) |  |
|**quality** | **String** | Quality of the localization | char(2) |  [optional] |
|**qualityNumeric** | **Long** | Quality as numeric value | int(10) |  [optional] |
|**region** | **String** | Event location remark region | varchar(255) |  [optional] |
|**rms** | **Double** | Root mean square | double |  [optional] |
|**secAzimGap** | **Float** | Secondary Azimutal gap | double |  [optional] |
|**wRms** | **Double** | Root mean square Weighted | double |  [optional] |
|**typeOrigin** | [**ObjectTypeOrigin**](ObjectTypeOrigin.md) |  |  [optional] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |
|**flags** | **String** | Flags for origin | varchar(255) |  [optional] [readonly] |
|**magnitudes** | [**List&lt;ObjectMagnitude&gt;**](ObjectMagnitude.md) |  |  [optional] |
|**arrivals** | [**List&lt;ObjectArrival&gt;**](ObjectArrival.md) |  |  [optional] |
|**focalmechanisms** | [**List&lt;ObjectFocalmechanism&gt;**](ObjectFocalmechanism.md) |  |  [optional] |



