# Upserting Documents

### Upsert Creates new document with given fields if document already exists then the fields gets updated 

## Upsert Query

Creates new document if not exists with fields specified in upsert key else if document exists then price will be updated

```
POST /product/default/2/_update
{
  "script": "ctx._source.price += 1000",
  "upsert": {
    "name" : "Kitchen",
    "specs" : {
      "finish" : "Glossy",
      "feature" : "HAFELE Hinges"
    },
    "price" : 8999,
    "discount" : 0
  }
}
```

## After Upsert

When Document is not present

```
{
  "_index" : "product",
  "_type" : "default",
  "_id" : "2",
  "_version" : 1,
  "_seq_no" : 6,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "name" : "Kitchen",
    "specs" : {
      "finish" : "Glossy",
      "feature" : "HAFELE Hinges"
    },
    "price" : 8999,
    "discount" : 0
  }
}
```

When Document is already present

```
{
  "_index" : "product",
  "_type" : "default",
  "_id" : "2",
  "_version" : 2,
  "_seq_no" : 7,
  "_primary_term" : 1,
  "found" : true,
  "_source" : {
    "name" : "Kitchen",
    "specs" : {
      "finish" : "Glossy",
      "feature" : "HAFELE Hinges"
    },
    "price" : 9999,
    "discount" : 0
  }
}
```