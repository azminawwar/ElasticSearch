# Data Types

## Core Data Types

### Text Data Type

Used to index full-text values such as description. These values are analyzed. They are rearly used for sorting and aggregation.

### Keyword Data Type

Used for structured data (tags, email). Not analyzed. Used for filtering and aggregation

### Numeric Data Types

These include float, long, byte, integer 

### Date Data Type

Represents dates as either a string , long or interger.

### Boolean Data Type

Stores true and false

### Binary Data Type

Accepts a BASE64 encoded binary values. 

### Range Data Type

Used for range values such as date range or numeric ranges.
ex. { "gte": 10, "lte": 20}

## Complex Data Types

### Object Data Type

Added as json objects, stored as key value pairs internally.


### Array Data Type

All values shoul have to be of same data type

### Nested Data Type

Special version of object data type. Enables array of objects to be querified independently of each other.


## Geo Data Types

### Geo-point Data Type

Accepts latitude-longitude pairs. Used for various geographical operations.

### Geo-shape Data Type

Used for more complex geographical shapes such as polygons, circles,etc.

## Specialized Data Types

### Ip Data Type 

This data type stores specific IP addresses

### Completion Data Type 

Used to provide auto-completion functionality.

### Attachment Data Type

Used to make text from various documents formats searchable
This requires a plugin sudo bin/elasticsearch-plugin install ingest-attachment