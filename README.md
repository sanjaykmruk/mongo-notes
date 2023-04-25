# Things to consider when using MongoDB

### When processing Kafka msg and saving in Mongo
- Use batch in both reading data from Kafka and Saving into MongoDB.

### When Sharding your data
- Make sure to use high cordality field as shard key

### When using TTL on a field for DB data management
- If you batch add data with same value for the TTL index field, then better change the logic to 
custom generate another field based on original TTL field value plus some random delay to avoid builk deletion of those record when TTL is triggered. 
This will avoid the DB load.

### When Sharding your DB
- Consider Region failure
- Consider more shard in place or region 
- consider IPOS required for the load

### When indexing
- follow the ESR[https://www.mongodb.com/docs/manual/tutorial/equality-sort-range-rule/] rule
