

# Hyp2000arcPhasesInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**net** | **String** | Channel net code | char(2) |  |
|**sta** | **String** | Channel station code | varchar(5) |  |
|**comp** | **String** | Channel code | char(3) |  |
|**loc** | **String** | Channel location | char(2) |  |
|**plabel** | **String** | Todo description | ??? |  [optional] |
|**slabel** | **String** | Todo description | ??? |  [optional] |
|**ponset** | **String** | Todo description | ??? |  [optional] |
|**sonset** | **String** | Todo description | ??? |  [optional] |
|**pat** | **OffsetDateTime** | Origin time | datetime(3) |  [optional] |
|**sat** | **OffsetDateTime** | Origin time | datetime(3) |  [optional] |
|**pres** | **Double** | Todo description | ??? |  [optional] |
|**sres** | **Double** | Todo description | ??? |  [optional] |
|**pqual** | **Double** | Todo description | ??? |  [optional] |
|**squal** | **Double** | Todo description | ??? |  [optional] |
|**codalen** | **Double** | Todo description | ??? |  [optional] |
|**codawt** | **Double** | Todo description | ??? |  [optional] |
|**pfm** | **String** | Todo description | ??? |  [optional] |
|**sfm** | **String** | Todo description | ??? |  [optional] |
|**datasrc** | **String** | Todo description | ??? |  [optional] |
|**md** | **Double** | Todo description | ??? |  [optional] |
|**azm** | **Double** | Todo description | ??? |  [optional] |
|**takeoff** | **Double** | Todo description | ??? |  [optional] |
|**dist** | **Double** | Todo description | ??? |  [optional] |
|**pwt** | **Double** | Todo description | ??? |  [optional] |
|**swt** | **Double** | Todo description | ??? |  [optional] |
|**pamp** | **Double** | Todo description | ??? |  [optional] |
|**codalenObs** | **Double** | Todo description | ??? |  [optional] |
|**ccntr** | **List** |  |  [optional] |
|**caav** | **List** |  |  [optional] |
|**amplitude** | **Float** | Amplitude (Normally peak-to-peak) | col55 F7.2 |  [optional] |
|**ampUnitsCode** | **Long** | Amp units code. 0&#x3D;PP mm, 1&#x3D;0 to peak mm (UCB), 2&#x3D;digital counts | col62 I2 |  [optional] |
|**ampType** | **Long** | Amplitude type 0&#x3D;unspecified 1&#x3D;Wood-Anderson 2&#x3D;velocity 3&#x3D;acceleration 4&#x3D;no magnitude | col114 I2 |  [optional] |
|**ampMag** | **Float** | Amplitude magnitude for this station | col98 F3.2 |  [optional] |
|**ampMagWeightCode** | **Long** | Amplitude magnitude weight code | col82 I1 |  [optional] |
|**importanceP** | **Float** | Importance of P arrival | col101 F4.3 |  [optional] |
|**importanceS** | **Float** | Importance of S arrival | col105 F4.3 |  [optional] |



