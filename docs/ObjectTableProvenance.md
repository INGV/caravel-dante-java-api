

# ObjectTableProvenance


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**id** | **Long** | Unique incremental id | bigint(20) |  [optional] [readonly] |
|**name** | **String** | Name of Provenance. i.e. INGV, ETH, USGS | varchar(255) |  [optional] |
|**softwarename** | **String** | Software name. i.e. SisPick, eqassemble, hypoinverse | char(255) |  [optional] |
|**version** | **String** | Version name | varchar(255) |  [optional] |
|**model** | **String** | Name/URI/DOI of the model | varchar(255) |  [optional] |
|**method** | **String** | Name/URI/DOI of the method | varchar(255) |  [optional] |
|**parameters** | **String** | Name/URI/DOI of the parameters | varchar(255) |  [optional] |
|**program** | **String** | Name/URI/DOI of the program | varchar(255) |  [optional] |
|**username** | **String** | User name | char(255) |  [optional] |
|**hostname** | **String** | Hostname | char(255) |  [optional] |
|**description** | **String** | Additional information | char(255) |  [optional] |
|**priority** | **Long** | Priority | int(8) |  [optional] |
|**evaluationmode** | **ProvenanceEvaluationmode** |  |  [optional] |
|**url** | **String** | External URL Reference | varchar(512) |  [optional] |
|**modified** | **OffsetDateTime** | Last Review | timestamp |  [optional] [readonly] |
|**inserted** | **OffsetDateTime** | Insert time | timestamp |  [optional] [readonly] |



