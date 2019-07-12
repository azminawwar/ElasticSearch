# Bulk Operations
For adding, updating and deleting multiple documents in single request

## Create Multiple Documents

```
POST /product/default/_bulk
{ "index": { "_id":"100"} }
{ "price": 100}
{ "index": { "_id":"101"} }
{ "price": 101 }
```

This created two documets with id 100 and 101

## Updating and Deleting using Bulk

```
POST /product/default/_bulk
{"update": {"_id": "100" } }
{"doc": {"price": 200 } }
{"delete": { "_id": "101" } }
```

After Executing the query

```
{
  "_index" : "product",
  "_type" : "default",
  "_id" : "100",
  "_version" : 2,
  "_seq_no" : 2,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "price" : 200
  }
}
```