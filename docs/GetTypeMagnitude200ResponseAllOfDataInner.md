

# GetTypeMagnitude200ResponseAllOfDataInner


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] |
|**name** | **String** | Type of the magnitude | varchar(255) |  [optional] |
|**priority** | **Long** | Type magnitude priority | int(8) |  [optional] |
|**minmag** | **Float** | Minimum magnitude value | float(4) |  [optional] |
|**maxmag** | **Float** | Maximum magnitude value | float(4) |  [optional] |
|**minreadings** | **Integer** | Minimum number of readings | int(8) |  [optional] |
|**description** | **String** | Additional information | char(255) |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |



