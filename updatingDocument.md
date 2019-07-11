# Updating Document

##  Before Updating

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

## Update Query (Adding price into existing document)

```
PUT /product/default/1
{
  "name": "Table",
  "specs": {
    "finish": "Walnut",
    "feature": "4 chairs"
  },
  "price": 12999
}
```

## After Update (Price field gets added into document and also version gets updated)
```
{
  "_index" : "product",
  "_type" : "default",
  "_id" : "1",
  "_version" : 2,
  "_seq_no" : 3,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "name" : "Table",
    "specs" : {
      "finish" : "Walnut",
      "feature" : "4 chairs"
    },
    "price" : 12999
  }
}
```