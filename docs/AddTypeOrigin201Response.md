

# AddTypeOrigin201Response


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**name** | **TypeOriginName** |  |  [optional] |
|**versionName** | **String** | Localization name (es:ew prelim,XX,WW,..) | varchar(255) |  [optional] |
|**versionValue** | **Long** | Define a numeric value for type origin. &lt; 100 is automatic location | bigint(20) |  [optional] |
|**description** | **String** | Additional information | char(255) |  [optional] |
|**priority** | **Long** | Type origin priority | tinyint(4) |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |



