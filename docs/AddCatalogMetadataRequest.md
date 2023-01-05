

# AddCatalogMetadataRequest


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**name** | **String** | Name of Catalog. i.e. INGV, ETH, USGS | varchar(255) |  |
|**doi** | **String** | DOI of Catalog. i.e. 10.13127/TDMT | varchar(255) |  [optional] |
|**description** | **String** | Additional information | char(255) |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |



