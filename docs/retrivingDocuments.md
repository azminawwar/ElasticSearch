## Retrive Documents with id
```
GET /product/default/1
```
```
Output: 
{
  "_index" : "product",
  "_type" : "default",
  "_id" : "1",
  "_version" : 1,
  "_seq_no" : 2,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "name" : "Table",
    "specs" : {
      "finish" : "Walnut",
      "feature" : "4 chairs"
    }
  }
}
```