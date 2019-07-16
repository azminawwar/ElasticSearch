# Changing Mapping of Index

## Adding Mapping to Exixting index

```
PUT /product/_mapping
{
  "properties": {
    "discount": {
      "type": "double"
    }
  }
}
```

## Changing Mapping of Exixting Index

It is not possible as previous documents may become invalid.

So we have to delete the whole index and recreate this 