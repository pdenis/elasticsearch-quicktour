INDEX
=====

Creation : POST /my_foo

Get info : GET /my_foo

Remove : DELETE /my_foo

Create a document

```json
POST /wiki/page/1
{
  "title": "My title",
  "text": "Helo world"
}
```

Update a document

```json
PUT /wiki/page/1
{
  "title": "My title",
  "text": "Helo world",
  "version": 2
}
```


Response : 
```json
{
   "_index": "wiki",
   "_type": "page",
   "_id": "1",
   "_version": 1,
   "created": true
}
```