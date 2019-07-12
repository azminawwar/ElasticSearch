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

## Alternative way of updating by giving only new and fields to be updated

```
POST /product/default/1/_update
{
  "doc": {
    "price": 11999,
    "discount": 1000
  }
}
```

## After Update (Price gets updated and discount gets added)

```
{
  "_index" : "product",
  "_type" : "default",
  "_id" : "1",
  "_version" : 3,
  "_seq_no" : 4,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "name" : "Table",
    "specs" : {
      "finish" : "Walnut",
      "feature" : "4 chairs"
    },
    "price" : 11999,
    "discount" : 1000
  }
}
```

## Update using Scripts
```
POST /product/default/1/_update
{
  "script": "ctx._source.price += 1000; ctx._source.discount -= 1000"
}
```

## After Updated (Price and Discount gets updated)

```
{
  "_index" : "product",
  "_type" : "default",
  "_id" : "1",
  "_version" : 4,
  "_seq_no" : 5,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "name" : "Table",
    "specs" : {
      "finish" : "Walnut",
      "feature" : "4 chairs"
    },
    "price" : 12999,
    "discount" : 0
  }
}
```