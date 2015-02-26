INDEX
=====

Creation : POST /my_foo

Get info : GET /my_foo

Remove : DELETE /my_foo

Create a document

POST /wiki/page/1
{
  "title": "My title",
  "text": "Helo world"
}

Update a document

PUT /wiki/page/1
{
  "title": "My title",
  "text": "Helo world",
  "version": 2
}
Response : 

{
   "_index": "wiki",
   "_type": "page",
   "_id": "1",
   "_version": 1,
   "created": true
}