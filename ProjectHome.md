## Moved to https://github.com/dpp-name/protobuf-json ##

Provide serialization and de-serialization of Google's protobuf Messages into/from [JSON format](http://www.json.org/). protobuf-json is written in python and depends on Google's [protobuf compiler](http://code.google.com/p/protobuf/) for python.

This code is in production for a year by now.

## Quick Example ##

Using .proto file like this:
```
 message Person {
   required int32 id = 1;
   required string name = 2;
   optional string email = 3;
 }
```
You can encod and decode it to/from json:
```
 {
  "id": 123,
  "name": "person name",
  "email": "user@example.com"
 }
```
More complex example:
```
 message Book {
   required string title = 1;
   optional float price = 2;
   repeated Person authors = 3;
 }
```
```
 {
  "title": "Book example",
  "price": 12.7,
  "authors": [
   {
    "id": 123,
    "name": "person name",
    "email": "user@example.com"
   },
   {
    "id": 456,
    "name": "another person",
   }
  ]
 }
```
## Todo ##
From version 2.3.0 protobuf protoc supports a plugin system for code generators. Plugins can generate code for new languages.<br />
TODO: write JavaScript code generator