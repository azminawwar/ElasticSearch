# Mapping

Mapping all about how we want our search results to come. Elastic Search has dyamic mapping inside. If we don't explicitly define any mapping then dynamic mapping comes into picture

## Getting Mapping of any index

```
GET /product/_mapping
```

Output

```
{
  "product" : {
    "mappings" : {
      "properties" : {
        "created" : {
          "type" : "date",
          "format" : "yyyy/MM/dd HH:mm:ss||yyyy/MM/dd||epoch_millis"
        },
        "description" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          }
        },
        "in_stock" : {
          "type" : "long"
        },
        "is_active" : {
          "type" : "boolean"
        },
        "name" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          }
        },
        "price" : {
          "type" : "long"
        },
        "sold" : {
          "type" : "long"
        },
        "tags" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          }
        }
      }
    }
  }
}

```