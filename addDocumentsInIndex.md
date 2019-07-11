## For creating new document with random id
```
POST /product/default
{
  "name": "Bed",
  "specs": {
    "finish": "Teek",
    "feature": "Single Bed"
  }
}
```
## For creating new document with custom id  
```
PUT /product/default/1
{
  "name": "Table",
  "specs": {
    "finish": "Walnut",
    "feature": "4 chairs"
  }
}
```