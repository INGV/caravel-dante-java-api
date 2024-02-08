

# ObjectMomenttensor


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |
|**idLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**originidOut** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**magnitudeidOut** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**setOriginidOutByOriginIdLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**setMagnitudeidOutByMagnitudeIdLocalspace** | **Long** | Localspace Id | bigint(19) |  [optional] |
|**scalarmoment** | **Double** | Scalar moment as derived in moment tensor inversion. Unit, Nm | double(22) |  [optional] |
|**mrr** | **Double** | mrr moment tensor component | double(22) |  [optional] |
|**mtt** | **Double** | mtt moment tensor component | double(22) |  [optional] |
|**mpp** | **Double** | mpp moment tensor component | double(22) |  [optional] |
|**mrt** | **Double** | mrt moment tensor component | double(22) |  [optional] |
|**mrp** | **Double** | mrp moment tensor component | double(22) |  [optional] |
|**mtp** | **Double** | mtp moment tensor component | double(22) |  [optional] |
|**clvd** | **Double** | CLVD (compensated linear vector dipole) parameter obtained from moment tensor inversion (decimal fraction between 0 and 1) | double(22) |  [optional] |
|**iso** | **Double** | Isotropic part obtained from moment tensor inversion (decimal fraction between 0 and 1) | double(22) |  [optional] |
|**url** | **String** | External URL Reference | varchar(512) |  [optional] |
|**varianceReduction** | **Double** | Variance reduction of moment tensor inversion, given in percent (Dreger 2003). This is a goodness-of-fit measure | double(22) |  [optional] |
|**doubleCouple** | **Double** | Double couple parameter obtained from moment tensor inversion (decimal fraction between 0 and 1) | double(22) |  [optional] |
|**typeMomenttensor** | **String** | Type of Moment Tensor | varchar(50) |  |
|**localspace** | [**ObjectLocalspace**](ObjectLocalspace.md) |  |  [optional] |
|**provenance** | [**ObjectProvenance**](ObjectProvenance.md) |  |  [optional] |
|**tdmt** | [**ObjectMomenttensorTdmt**](ObjectMomenttensorTdmt.md) |  |  [optional] |
|**rcmt** | [**ObjectMomenttensorRcmt**](ObjectMomenttensorRcmt.md) |  |  [optional] |



