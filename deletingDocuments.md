# Deleting Document

## Delete Single Document with ID

```
DELETE /product/default/3
```

## Deleting Multiple Documnets with match

```
POST /product/_delete_by_query
{
  "query": {
    "match": {
      "name": "Bed"
    }
  }
}
```