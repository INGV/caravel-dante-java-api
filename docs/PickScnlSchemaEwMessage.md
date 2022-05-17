

# PickScnlSchemaEwMessage


## Properties

| Name | Type | Description | Notes |
|------------ | ------------- | ------------- | -------------|
|**pickId** | **Long** | Localspace Id | bigint(19) |  |
|**network** | **String** | Channel net code | char(2) |  [optional] |
|**station** | **String** | Channel station code | varchar(5) |  [optional] |
|**component** | **String** | Channel code | char(3) |  [optional] |
|**location** | **String** | Channel location | char(2) |  [optional] |
|**firstMotion** | **PickFirstmotion** |  |  [optional] |
|**pickWeight** | **Float** | Uncertainty as the absolute value of deviation from the mainvalue towards smaller values. | decimal(8,3) |  [optional] |
|**timeOfPick** | **OffsetDateTime** | Arrival time with microseconds | datetime(3) |  [optional] |
|**pAmplitude** | **List&lt;Double&gt;** |  |  [optional] |



