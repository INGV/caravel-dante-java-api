

# ObjectTableLocalspace


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**name** | **String** | Localspace name. i.e. hew1_mole, endeavour_mole | char(255) |  [optional] |
|**doi** | **String** | DOI Resource. i.e. 10.13127/TDMT | varchar(255) |  [optional] |
|**description** | **String** | Additional information | char(255) |  [optional] |
|**priority** | **Long** | Priority | int(8) |  [optional] |
|**environment** | **Environment** |  |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |



