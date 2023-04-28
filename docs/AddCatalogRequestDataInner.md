

# AddCatalogRequestDataInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**name** | **String** | Localspace name. i.e. hew1_mole, endeavour_mole | char(255) |  |
|**doi** | **String** | DOI Resource. i.e. 10.13127/TDMT | varchar(255) |  [optional] |
|**eventid** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**originid** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**magnitudeid** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**eventGroupId** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |



