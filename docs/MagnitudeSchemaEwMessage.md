

# MagnitudeSchemaEwMessage


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**quakeId** | **Long** | Localspace Id | bigint(19) |  |
|**version** | **TypeOriginName** |  |  |
|**mag** | **Double** | Magnitude value | double |  |
|**error** | **Double** | Magnitude error | double |  [optional] |
|**quality** | **Double** | quality | double |  [optional] |
|**minDist** | **Double** | Minimal distance from station to origin | double |  [optional] |
|**azimuth** | **Float** | Azimutal gap | float4 |  [optional] |
|**nStations** | **Long** | Number of the stations on magnitudo calculation | int(11) |  [optional] |
|**nChannels** | **Long** | Number of the channel on magnitudo calculation | int(11) |  [optional] |
|**qAuthor** | **String** | qAuthor description |  [optional] |
|**qddsVersion** | **Double** | qddsVersion description |  [optional] |
|**iMagType** | **Double** | iMagType description |  [optional] |
|**magType** | **String** | Type of the magnitude | varchar(255) |  [optional] |
|**algorithm** | **Double** | algorithm description |  [optional] |
|**ingvQuality** | **String** | INGV quality code of the magnitude (computed by ew2moledb) | char(2) |  [optional] |
|**phases** | [**List&lt;MagnitudePhasesInner&gt;**](MagnitudePhasesInner.md) |  |  [optional] |



