## For Creating Document with random ID
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
## For Creating Document with Custom ID  
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