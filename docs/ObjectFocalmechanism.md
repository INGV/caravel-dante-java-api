

# ObjectFocalmechanism


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**strike1** | **Integer** | strike focal plane n.1 | int(10) |  [optional] |
|**dip1** | **Integer** | dip focal plane n.1 | int(10) |  [optional] |
|**rake1** | **Integer** | rake focal plane n.1 | int(10) |  [optional] |
|**strike2** | **Integer** | strike focal plane n.2 | int(10) |  [optional] |
|**dip2** | **Integer** | dip focal plane n.2 | int(10) |  [optional] |
|**rake2** | **Integer** | rake focal plane n.2 | int(10) |  [optional] |
|**azimGap** | **Float** | Largest azim gap as seen from epicenter | double(22) |  [optional] |
|**nstaPolarity** | **Integer** | Number of station polarities used for determination | int(10) |  [optional] |
|**misfit** | **Double** | Fraction of misfit polarities [0,1] | double(22) |  [optional] |
|**stdr** | **Double** | Station distribution ratio parameter [0,1] | double(22) |  [optional] |
|**rmsAngDiffAccPref** | **Double** | rms_ang_diff_acc_pref | double(22) |  [optional] |
|**fracAcc30degPref** | **Double** | frac_acc_30deg_pref | double(22) |  [optional] |
|**quality** | **String** | quality | char(2) |  [optional] |
|**url** | **String** | url pdf file | varchar(255) |  [optional] |
|**momenttensor** | [**ObjectMomenttensor**](ObjectMomenttensor.md) |  |  [optional] |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |



